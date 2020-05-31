---
layout: post
title: Setting up a new Windows 7 instance
tags: [win7]
---

This represents my notes on a new Windows 7 setup. It assumes that I
have already activated it and installed updates, etc.

Yes, I know Windows 7 is unsupported. So what?

1. Set performance in computer properties -> advanced -> performance
  * turn off all except font smoothing
1. Set for auto login, using "netplwiz"
1. Connect to mac volume pub as "net use v: \\10.0.1.211\pub"
2. Get and install [firefox](https://www.mozilla.org/en-US/firefox/new/)
2. Install TCC from https://jpsoft.com/products/tcc-le.html
  * install to c:\tcc no matter what the installer wants to do
  * copy the [aliases](../../win7/tcc/aliases)
  * copy the [startup](../../win7/tcc/4start.bat)
  * put a link to tcc on the desktop
1. Make a directory for tools c:\usr
1. Get [7zip](https://www.7-zip.org/download.html) and install in c:\usr\7zip
2. Install [ztreewin](https://www.ztree.com/html/beta.htm) in c:\usr\ztree
1. Set the system variable HOME to somewhere sane; c:\rcvn
  * in computer properties -> advanced -> environment variables
3. Install [emacs for windows](https://ftp.gnu.org/gnu/emacs/windows/) into c:\emacs
3. Put a .emacs file into HOME
1. install [gitforwindows](https://gitforwindows.org/)
1. Install [tortoisegit]()
  * tortoisegit doesn't seem to integrate to explorer ???
1. install [powerpro](http://powerpro.cresadu.com/) to c:\usr\powerpro


  
  
