# Lumen Updates

sudo rm -rf /var/lib/apt/lists/partial/*lumen-updates*

sudo rm -f /var/lib/apt/lists/*lumen-updates*

sudo apt-get -o Acquire::https::No-Cache=true -o Acquire::http::No-Cache=true update

grep -c "Version: 1.2.0" /var/lib/apt/lists/*lumen-updates*Packages*

apt-cache policy lumen-release

SISISISISSIS
ls -l /var/lib/apt/lists/*lumen-updates*


etttt
sudo apt-get install -y --reinstall lumen-release
