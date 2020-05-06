
```

# on corp machine
# local ssh directory that is writable
mkdir ~/etc
mkdir ~/etc/ssh
ssh-keygen -t dsa -f ~/etc/ssh/ssh_host_dsa_key
ssh-keygen -t rsa -f ~/etc/ssh/ssh_host_rsa_key

# run sshd
/usr/bin/sshd -h ~/etc/ssh/ssh_host_rsa_key

# reverse tunnel to local machine
ssh -R 2222:localhost:22 me@192.168.1.211

# on local machine
ssh corp.user@localhost -p 2222

# maybe? tunnel a proxy for web
ssh -D 8888 corp.user@localhost -p 2222
```
