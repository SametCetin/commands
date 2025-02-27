# Windows Wsl

##### Kurulu makineleri listele :
    wsl -l

##### Kurulu makineleri detaylı listele :
    wsl -l -v

##### Çalışan makineyi dağıtıma göre kapat:
    wsl --terminate Ubuntu
    
##### Çalışan makineyi kapat :
    wsl --shutdown
    
##### Çalışan makineleri listele
    wsl --list --running

##### Debian indir ve kur 
    wsl --install -d Debian

##### Debian makinesini çalıştır
    wsl -d Debian
    
##### Wsl konsoldan lokal konsola çıkma
    exit

##### Makine sil (Ubuntu)
    wsl --unregister Ubuntu

