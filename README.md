# Lumen Updates

sudo rm -f /var/lib/apt/lists/*lumen-updates*

sudo apt-get -o Acquire::https::No-Cache=true update

apt-cache policy lumen-release

sudo apt-get install --only-upgrade lumen-release


SISISIS
grep -A3 "^Package: lumen-release" /var/lib/apt/lists/*lumen-updates*Packages* 2>/dev/null | head -20
