---
layout: post
title: Schlock Mercenary
tags: Comics, PHP
date: 2020-07-27 22:38:43 -0500
---

I've been reading [Schlock Mercenary](https://www.schlockmercenary.com) for about
5 years now; Howard Tayler has provided much entertainment for me. Thanks, Howard!

However he just finished 20 years of Schlock and is taking a well-deserved
hiatus. This leaves me is a bad spot -- nothing to entertain me with.

I noticed the date format of the web archive of the strip, and realized that
if I simply subtract 20 years from the current date, I will get a valid URL
from the first Schlock book. If I script that, I can get a new comic every day
until Howard starts writing again!!!!

PHP. I know, I know... Whatcha gonna do?

```
<!DOCTYPE html>
<html>
<body>

<?php
$d=date("Y")-20 . "-" . date("m") . "-" . date("d") ;
$xx = "<a href=\"https://www.schlockmercenary.com/" . $d . "\">schlock</a>";
$yy = "https://www.schlockmercenary.com/" . $d;
header('Location: ' . $yy, true, 302);              // Use either 301 or 302
exit(0);
# echo $xx;
?>

</body>
</html>
```
