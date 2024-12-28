
## Firewall 

### Kurulum
```bash
  sudo dnf install firewalld
  sudo systemctl start firewalld
  sudo systemctl enable firewalld
  sudo systemctl status firewalld
  sudo firewall-cmd --list-all 
```

### Port ekleme / kaldırma
```bash
  sudo firewall-cmd --permanent --add-port=8080/tcp # kural ekle
  sudo firewall-cmd --permanent --remove-port=8080/tcp # kural kaldır
  sudo firewall-cmd --permanent --add-port=1194/udp
  sudo firewall-cmd --reload # değişiklikleri uygula
```

### Hizmetlere izin verme
```bash
  sudo firewall-cmd --permanent --add-service=ftp
  sudo firewall-cmd --permanent --add-service=ssh
  sudo firewall-cmd --permanent --add-service=http
  sudo firewall-cmd --permanent --add-service=https
```

## Gnome masaüstü kurulumu
```bash
  sudo dnf groupinstall "Server with GUI"
```

