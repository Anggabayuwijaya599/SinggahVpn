## CARA INSTALL SCRIPT SINGGAH VPN


### 1. DAFTARKAN DAHULU IP VPS YANG AKAN KITA INSTAL DI LINK BERIKUT INI :

=== https://github.com/Anggabayuwijaya599/ijin/blob/main/ipvps          

### 2. COPY PASTE SCRIPT INSTALLER BERIKUT KE DALAM VPS YANG MAU KITA INSTALL :

```
apt install -y && apt update -y && apt upgrade -y && wget -q https://raw.githubusercontent.com/Anggabayuwijaya599/installsinggah/refs/heads/main/vpn && chmod +x vpn && ./vpn
```


### 3.MASUKAN DOMAIN YANG SUDAH DI POINTING KE CLOUDFLARE SAAT INSTTALASI SCRIPT

### 4.TUNNGGU PROSSES INSTALL SAMPAI SELESAI JANGAN SAMPAI TERPUTUS KONEKSI SAAT INSTALL SEBAB AKAN MENGULANG DARI STEP PERTAM
JIKA SELESAI INSTALL MINTA REBOOT, TEKAN ENTER UNTUK REBOOT.

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
sudo systemctl status xray
sudo journalctl -u xray -f
      
### 6. SELESAI PROSSES INSTALLASI SELESAI DAN VPS SIAP DI GUNAKAN




```


