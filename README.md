# lumen-updates

curl -fLO https://raw.githubusercontent.com/SffeeRoro233/lumen-updates/main/activation/lumen-release_0.4.1_all.deb
echo "18eeb2aebb667c3d9fde3e0013b88130b5133108830652ddcfa5da9ff4a50ca9  lumen-release_0.4.1_all.deb" | sha256sum -c -

sudo apt install ./lumen-release_0.4.1_all.deb
