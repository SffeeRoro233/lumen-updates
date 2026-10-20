# Lumen Updates

sudo sh -c 'echo "deb [signed-by=/usr/share/keyrings/lumen-updates.gpg] https://raw.githubusercontent.com/SffeeRoro233/lumen-updates/main/repo/v1.3.0/ ./" > /etc/apt/sources.list.d/lumen-updates.list'
sudo apt-get update ; sudo apt-get install -y lumen-release
