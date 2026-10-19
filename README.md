# Lumen Updates

echo "=== VERSION INSTALLEE ==="
cat /var/lib/lumen-updater/release-installed.json 2>&1
dpkg -l lumen-release 2>&1 | tail -2

echo "=== SOURCE LUMEN ==="
cat /etc/apt/sources.list.d/lumen-updates.list 2>&1

echo "=== CLE PUBLIQUE ==="
ls -l /usr/share/keyrings/lumen-updates.gpg 2>&1

echo "=== MISE A JOUR APT ==="
sudo apt-get update 2>&1 | tail -15

echo "=== VERSION PROPOSEE ==="
apt-cache policy lumen-release 2>&1

echo "=== DERNIER ETAT DE L'OUTIL ==="
cat /var/lib/lumen-updater/status.json 2>&1
