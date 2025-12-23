## CARA INSTALL SCRIPT SINGGAH VPN


### 1. DAFTARKAN DAHULU IP VPS YANG AKAN KITA INSTAL DI LINK BERIKUT INI :

=== https://github.com/Anggabayuwijaya599/ijin/blob/main/ipvps          

### 2. COPY PASTE SCRIPT INSTALLER BERIKUT KE DALAM VPS YANG MAU KITA INSTALL :

```
apt install -y && apt update -y && apt upgrade -y && wget -q https://raw.githubusercontent.com/Anggabayuwijaya599/installsinggah/refs/heads/main/vpn && chmod +x vpn && ./vpn
```


### 3.MASUKAN DOMAIN YANG SUDAH DI POINTING KE CLOUDFLARE SAAT INSTTALASI SCRIPT

### 4.TUNNGGU PROSSES INSTALL SAMPAI SELESAI JANGAN SAMPAI TERPUTUS KONEKSI SAAT INSTALL SEBAB AKAN MENGULANG DARI STEP PERTAM
JIKA SELESAI INSTALL MINTA REBOOT, TEKAN <B>ENTER</B> UNTUK REBOOT.

### 5. TURUNKAN VERSI XRAY AGAR XRAY BISA BERJALAN DENGAN CARA COPY PASTE PERINTAH BERIKUT KE DALAM VPS

```
sudo systemctl stop xray
sudo mv /usr/local/bin/xray /usr/local/bin/xray.bak.v25.10
wget https://github.com/XTLS/Xray-core/releases/download/v25.1.30/Xray-linux-64.zip
unzip Xray-linux-64.zip
sudo mv xray /usr/local/bin/xray
sudo chmod +x /usr/local/bin/xray
/usr/local/bin/xray version
sudo systemctl start xray
sudo systemctl enable xray
```

### 6. SELESAI PROSSES INSTALLASI SELESAI DAN VPS SIAP DI GUNAKAN



================================= JIKA VPS UBUNTU LEBIH DARI UBUNTU 20.0.4 WAJIB DOWNGRADE KE UBUNTU 20.0.4========================
###  COPY PASTE LINK BERIKUT UNTUK DOWNGRADE VPS KE UBUNTU 20


```
wget https://raw.githubusercontent.com/Anggabayuwijaya599/SinggahVpn/refs/heads/main/install-ulang
chmod +x install-ulang
./install-ulang
```

- PILIH NOMOR 2.UBUNTU
- PILIH VERSI NOMOR 1 . 20.04
- krtika di minta masukan atau ketikan huruf Y ( lalu ENTER )
- TUNGGU PROSSES NYA KURANG LEBIH 10 MENIT
- SELESAI MASUK SUDAH BERUBAH MENJADI UBUNTU 20.04





#### UPDATE SCRIPT :
```
wget -q https://raw.githubusercontent.com/Anggabayuwijaya599/SinggahVpn/refs/heads/main/update.sh && chmod +x update.sh && ./update.sh

```

### UNTUK INSTALL UDP JIKA TIDAK JALAN COPY PASTE DI SCRIPT OTOMATIS SETELAH INSTALL AKAN REBOOT ::

```
#!/bin/bash

cd
rm -rf /root/udp
mkdir -p /root/udp

# change to time GMT+7
echo "change to time GMT+7"
ln -fs /usr/share/zoneinfo/Asia/Jakarta /etc/localtime

# install udp-custom
echo downloading udp-custom
wget -q --show-progress --load-cookies /tmp/cookies.txt "https://docs.google.com/uc?export=download&confirm=$(wget --quiet --save-cookies /tmp/cookies.txt --keep-session-cookies --no-check-certificate 'https://docs.google.com/uc?export=download&id=1ixz82G_ruRBnEEp4vLPNF2KZ1k8UfrkV' -O- | sed -rn 's/.*confirm=([0-9A-Za-z_]+).*/\1\n/p')&id=1ixz82G_ruRBnEEp4vLPNF2KZ1k8UfrkV" -O /root/udp/udp-custom && rm -rf /tmp/cookies.txt
chmod +x /root/udp/udp-custom

echo downloading default config
wget -q --show-progress --load-cookies /tmp/cookies.txt "https://docs.google.com/uc?export=download&confirm=$(wget --quiet --save-cookies /tmp/cookies.txt --keep-session-cookies --no-check-certificate 'https://docs.google.com/uc?export=download&id=1klXTiKGUd2Cs5cBnH3eK2Q1w50Yx3jbf' -O- | sed -rn 's/.*confirm=([0-9A-Za-z_]+).*/\1\n/p')&id=1klXTiKGUd2Cs5cBnH3eK2Q1w50Yx3jbf" -O /root/udp/config.json && rm -rf /tmp/cookies.txt
chmod 644 /root/udp/config.json

if [ -z "$1" ]; then
cat <<EOF > /etc/systemd/system/udp-custom.service
[Unit]
Description=UDP Custom by ePro Dev. Team

[Service]
User=root
Type=simple
ExecStart=/root/udp/udp-custom server
WorkingDirectory=/root/udp/
Restart=always
RestartSec=2s

[Install]
WantedBy=default.target
EOF
else
cat <<EOF > /etc/systemd/system/udp-custom.service
[Unit]
Description=UDP Custom by ePro Dev. Team

[Service]
User=root
Type=simple
ExecStart=/root/udp/udp-custom server -exclude $1
WorkingDirectory=/root/udp/
Restart=always
RestartSec=2s

[Install]
WantedBy=default.target
EOF
fi

echo start service udp-custom
systemctl start udp-custom &>/dev/null

echo enable service udp-custom
systemctl enable udp-custom &>/dev/null

echo reboot
reboot

```


# Install ZIVPN

```
cd root
wget https://github.com/Anggabayuwijaya599/SinggahVpn/raw/refs/heads/main/zivpn
chmod +x zivpn
./zivpn
```


