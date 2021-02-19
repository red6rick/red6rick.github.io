---
layout: post
title: OpenWRT DHCP Management
tags:
date: 2021-02-19 13:16:02 -0600
---
I use an [openwrt]() router for my home system. I want control of ip assignments
on my network, but I want the DHCP server running. OpenWRT makes this possible,
but requires the /etc/hosts and /etc/ethers files to track each other.

Hosts contains an IP -> Name association; ethers maps a mac address to a name
or an ip address -- preferably both. I wrote this script to automate the
correlation so I only have to manage one file.

~~~~
#!/bin/sh
# one-stop shopping for dhcp reservations on open-wrt

# a file containing a sed script to parse the embedded ip/mac/name info
# from the file; an embedded awk script to parse this data into hosts
# and ethers. these are copied into etc, and the dns servers are restarted

# capture everything between the begin and end data tags and pipe to awk

sed -e '/[B]EGIN_DATA/,/[E]ND_DATA/!d' $0 | awk '

# lines to transfer directly go into hosts
/^# / {   
    gsub(/^# +/,"");
    print >"hosts";
    next;
}

# lines containing a mac address
$2 ~ /..:..:..:..:..:../ {
        ip = "10.0.1." $1;  mac = $2;  name = $3;
        printf("%s %s\n",ip,name) >"hosts";
        printf("%s %s\n",mac,name) >"ethers";
        printf("%s %s\n",mac,ip) >"ethers";
}
'

cp hosts /etc
cp ethers /etc

/etc/init.d/dnsmasq restart
/etc/init.d/odhcpd restart

exit

######################################################################
#BEGIN_DATA

# # header, required for hosts
# 127.0.0.1 localhost
# ::1     localhost ip6-localhost ip6-loopback
# ff02::1 ip6-allnodes
# ff02::2 ip6-allrouters
# #
# # my local data; ip, mac, name. parsed into hosts and ethers
# #
002 00:11:32:D6:DD:AF nas
003 d8:0d:17:4e:04:d0 router-sheshed
004 b0:95:75:32:ff:8e router-mancave
# # etc...t

#END_DATA
~~~~
