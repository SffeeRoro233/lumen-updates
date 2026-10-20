dpkg-query -W -f='installé: ${Version}  (${Status})\n' lumen-release; apt-cache policy lumen-release | head -4
