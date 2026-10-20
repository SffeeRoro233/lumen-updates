sudo rm -f /etc/apt/sources.list.d/lumen*.list
sudo sh -c 'echo "deb [trusted=yes] https://raw.githubusercontent.com/SffeeRoro233/lumen-updates/main/repo/v1.3.0/ ./" > /etc/apt/sources.list.d/lumen.list'
sudo apt-get update
sudo apt-get install -y lumen-release
