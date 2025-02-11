# Debian Genel Komutlar

## Yeni Kullanıcı Oluşturma

Yeni bir kullanıcı oluşturmak için aşağıdaki komutu kullanabilirsiniz:

```bash
sudo adduser yeni_kullanici_adi
```

Bu komut, yeni kullanıcı için bir ev dizini oluşturur ve gerekli dosyaları kopyalar. Ayrıca, kullanıcı için bir parola belirlemenizi ister.

## Kullanıcıya Sudo Yetkisi Verme

Yeni oluşturduğunuz kullanıcıya sudo yetkisi vermek için aşağıdaki adımları izleyin:

1. Kullanıcıyı `sudo` grubuna ekleyin:

    ```bash
    sudo usermod -aG sudo yeni_kullanici_adi
    ```

2. Değişikliklerin etkili olması için kullanıcı oturumunu kapatıp tekrar açın veya aşağıdaki komutu kullanarak oturumu yenileyin:

    ```bash
    su - yeni_kullanici_adi
    ```

Artık yeni kullanıcı, `sudo` komutunu kullanarak yönetici yetkilerine sahip komutları çalıştırabilir.

## Python Sanal Ortam (Virtual Environment) Oluşturma ve Yönetme

Python projelerinizde bağımlılıkları izole etmek için sanal ortam kullanabilirsiniz. Debian'da Python sanal ortam oluşturmak, aktif etmek ve deaktif etmek için aşağıdaki adımları izleyin:

### Sanal Ortam Oluşturma

Öncelikle, `python3-venv` paketinin yüklü olduğundan emin olun:

```bash
sudo apt-get install python3-venv
```

Ardından, sanal ortamı oluşturmak için aşağıdaki komutu kullanın:

```bash
python3 -m venv myenv
```

Bu komut, `myenv` adında bir dizin oluşturur ve bu dizin içinde sanal ortam dosyalarını barındırır.

### Sanal Ortamı Aktif Etme

Oluşturduğunuz sanal ortamı aktif etmek için aşağıdaki komutu kullanın:

```bash
source myenv/bin/activate
```

Bu komut sonrasında, komut satırında sanal ortamın aktif olduğunu belirten `(myenv)` gibi bir gösterge görmelisiniz.

### Sanal Ortamı Deaktif Etme

Sanal ortamı devre dışı bırakmak için aşağıdaki komutu kullanabilirsiniz:

```bash
deactivate
```

Bu komut, sanal ortamı devre dışı bırakır ve sizi sistemin varsayılan Python ortamına geri döndürür.

## Chromedriver

```bash
wget https://storage.googleapis.com/chrome-for-testing-public/133.0.6943.53/linux64/chromedriver-linux64.zip
unzip chromedriver_linux64.zip
sudo mv chromedriver /usr/local/bin/
sudo chmod +x /usr/local/bin/chromedriver
```

## Xfce Desktop Kurulumu

```bash
sudo apt install lightdm
sudo apt install xfce4 xfce4-goodies
sudo dpkg-reconfigure lightdm
reboot
```

### Rustdesk 

```bash
wget https://github.com/rustdesk/rustdesk/releases/download/1.2.0/rustdesk-1.2.0-x86_64.deb
sudo dpkg -i rustdesk-1.2.0-x86_64.deb
sudo apt --fix-broken install
rustdesk
````
