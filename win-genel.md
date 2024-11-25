# Windows Genel

***

## Otomatik logOn - şifreli kullanıcı
1. HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon,
2. AutoAdminLogon değerini 1 yap,
3. DefaultUserName değerini yaz,
4. DefaultPassword değerini yaz, yoksa yeni string ekle

***
### Sanal PC local hostunda dışa tünel açma
ssh -L 4840:127.0.0.1:4840 kullanici@sanalpcexternalip
Örnke: ssh -L 4840:127.0.0.1:4840 Administrator@192.168.133.128
***
