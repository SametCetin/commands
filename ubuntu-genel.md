# Ubuntu Genel

## AppImage Integration araç kurulumu

```shell
sudo apt install libfuse2
sudo apt install software-properties-common
sudo add-apt-repository ppa:appimagelauncher-team/stable
sudo apt update
sudo apt install appimagelauncher
```

## Chrome kurulumu

```bash
wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | sudo apt-key add -
sudo sh -c 'echo "deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google-chrome.list'
sudo apt update
sudo apt install google-chrome-stable
```

## Dosya oluştur

```bash
touch dosyaadi.txt
```

## exfat biçimlendirme özelliği ekleme

```shell
sudo apt-get update
sudo apt-get install exfat-fuse exfatprogs
lsblk ## cihazları listele
sudo mkfs.exfat /dev/sdX ## X yerine cihazın harfini yaz
```

## gcc-12 kurulum

```shell
sudo apt install gcc-12 g++-12
```

## gnome eklentiler

```shell
sudo apt install gnome-tweaks
sudo apt install dconf-editor
```

## Masaüstü ortamı

```bash
sudo apt update
sudo apt install tasksel
sudo tasksel
sudo reboot
```

## python3

### pip

```bash
apt install python3-pip 
```

### Selenium

```bash
pip install selenium
```

## snap uygulama mağazasını güncelleme kodu

```shell
sudo snap refresh snap-store
```

## sudoer kullanıcı ekleme

```shell
su -                        # roota geç
usermod -aG sudo <username> # kullanıcıyı sudoer yap
groups <username>           # kullanıcı yetki bilgisi
su <username>               # kullanıcıya geç
sudo apt update             # sudo yetki test et
```

## uzak pcden dosya indirme

```bash
# örnek:
scp user@sunucu-ip:/home/user/filename.txt ~/Downloads/
```
