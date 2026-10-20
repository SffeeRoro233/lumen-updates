# Lumen Updates

echo "--- paquet ---"; dpkg-query -W -f='${Package} ${Version}\n' lumen-release
echo "--- version enregistree ---"; cat /var/lib/lumen-updater/release-installed.json
echo "--- source APT ---"; cat /etc/apt/sources.list.d/lumen-updates.list
echo "--- ce qu'APT propose ---"; apt-cache policy lumen-release | head -6
