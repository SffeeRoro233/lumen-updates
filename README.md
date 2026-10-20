romain@romain-aspiregx781:~$ sudo ls -1 /etc/apt/sources.list.d/ ; sudo grep -r . /etc/apt/sources.list.d/ /etc/apt/sources.list 2>/dev/null
lumen.list
lumen-updates.list
/etc/apt/sources.list.d/lumen.list:deb [trusted=yes] https://raw.githubusercontent.com/SffeeRoro233/lumen-updates/main/repo/v1.3.0/ ./
/etc/apt/sources.list.d/lumen-updates.list:deb [signed-by=/usr/share/keyrings/lumen-updates.gpg] https://raw.githubusercontent.com/SffeeRoro233/lumen-updates/main/repo/v1.3.0/ ./
/etc/apt/sources.list:deb https://deb.debian.org/debian trixie main contrib non-free-firmware
/etc/apt/sources.list:deb https://deb.debian.org/debian trixie-updates main contrib non-free-firmware
/etc/apt/sources.list:deb https://security.debian.org/debian-security trixie-security main contrib non-free-firmware
