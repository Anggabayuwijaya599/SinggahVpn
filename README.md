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
>>> ganti (PASSWORD_KAMU) MEnjadi pasword vps yang mudah di ingat

```
curl -O https://raw.githubusercontent.com/hokagelegend9999/alpha.v2/refs/heads/main/reinstall.sh
chmod +x reinstall.sh
bash reinstall.sh debian 11 --password PASSWORD_KAMU
```





