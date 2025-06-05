# pCloud rclone ile kullanım notları

## rclone config ayarı

Kaynak linki: [https://rclone.org/pcloud]

```bash
rclone config
# No remotes found, make a new one?
# n) New remote
# s) Set configuration password
# q) Quit config
n/s/q> n
name> remote
# Type of storage to configure.
# Choose a number from below, or type in your own value
# [snip]
# XX / Pcloud
#    \ "pcloud"
# [snip]
Storage> pcloud
# Pcloud App Client Id - leave blank normally.
client_id> 
# Pcloud App Client Secret - leave blank normally.
client_secret> 
# Edit advanced config?
# y) Yes
# n) No (default)
y/n> n
Remote config
# Use web browser to automatically authenticate rclone with remote?
#  * Say Y if the machine running rclone has a web browser you can use
#  * Say N if running rclone on a (remote) machine without web browser access
# If not sure try Y. If Y failed, try N.
# y) Yes
# n) No
y/n> y
# If your browser doesn't open automatically go to the following link: http://127.0.0.1:53682/auth
# Log in and authorize rclone for access
# Waiting for code...
# Got code
# Configuration complete.
# Options:
# - type: pcloud
# - client_id:
# - client_secret:
# - token: {"access_token":"XXX","token_type":"bearer","expiry":"0001-01-01T00:00:00Z"}
# Keep this "remote" remote?
# y) Yes this is OK
# e) Edit this remote
# d) Delete this remote
y/e/d> y

```
## alt klasör için alias ekleme
```bash
rclone config
n/s/q> n
name> remote_subFolder
Storage> alias
remote> remote:subFolder
# Edit advanced config
y/n> n
# Keep this remote ?
y/e/d> y
```

## rclone web arayüz için
```bash
rclone rcd --rc-web-gui
```
### rclone mount örnekleri
```bash
Start-Process -WindowStyle Hidden rclone -ArgumentList "mount remote:Work D:\pcloudBM\Work --vfs-cache-mode=full --dir-cache-time=12h --vfs-read-chunk-size=16M --vfs-read-chunk-size-limit=512M --buffer-size=32M"

rclone mount remote:Work D:\pcloudBM\Work --vfs-cache-mode=full --dir-cache-time=12h --vfs-read-chunk-size=16M --vfs-read-chunk-size-limit=512M --buffer-size=32M

rclone mount remote:Work D:\pcloudBM\Work --vfs-cache-mode=full --dir-cache-time=12h --vfs-read-chunk-size=16M --vfs-read-chunk-size-limit=512M --buffer-size=32M --links

rclone mount remote:Work D:\pcloudBM\Work --vfs-cache-mode=full --dir-cache-time=12h --vfs-read-chunk-size=16M --vfs-read-chunk-size-limit=512M --buffer-size=32M --links

Start-Process -WindowStyle Hidden -FilePath "C:\rclone\rclone.exe" -ArgumentList "mount remote:Work D:\pcloudBM\Work --vfs-cache-mode=full --dir-cache-time=12h --vfs-read-chunk-size=16M --vfs-read-chunk-size-limit=512M --buffer-size=32M"
```

## nssm ile servis ile start

```bash
> nssm install # gui açar
```
- Path kısmına rclone programı yolu seçilir.  
- Açılan ekranda Arguments kısmına aşağıdakine benze uyumlu bilgiler yazılır;  
    --config "C:\Users\scHaffner\AppData\Roaming\rclone\rclone.conf" mount pCloudBmWork: d:\pcloudBM\Work --vfs-cache-mode writes
- Log on kısmına oturum açan kullanıcı ve varsa şifresi yazılmalı

