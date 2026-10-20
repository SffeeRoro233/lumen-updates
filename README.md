# Lumen Updates

command -v sudo || echo "sudo absent"; ls -l /usr/lib/lumen/update-helper


su -c '/usr/lib/lumen/update-helper release-upgrade'
