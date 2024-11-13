# VMWare-vmmon-vmnet-error-fix

**Run these commands in your terminal**  

```bash
openssl req -new -x509 -newkey rsa:2048 -keyout VMWARE17.priv -outform DER -out VMWARE17.der -nodes -days 36500 -subj "/CN=VMWARE/"
```

## Mint

```bash
sudo /usr/src/linux-headers-$(uname -r)/scripts/sign-file sha256 ./VMWARE17.priv ./VMWARE17.der $(modinfo -n vmmon)
sudo /usr/src/linux-headers-$(uname -r)/scripts/sign-file sha256 ./VMWARE17.priv ./VMWARE17.der $(modinfo -n vmnet)
```

## Fedora

```bash
sudo /usr/src/kernels/6.7.4-200.fc39.x86_64/scripts/sign-file sha256 ./VMWARE17.priv ./VMWARE17.der $(modinfo -n vmmon)
sudo /usr/src/kernels/6.7.4-200.fc39.x86_64/scripts/sign-file sha256 ./VMWARE17.priv ./VMWARE17.der $(modinfo -n vmmon)
```

```bash
tail $(modinfo -n vmmon) | grep "Module signature appended"

sudo mokutil --import VMWARE17.der
```

**After you have finished all of the commands above, you need to reboot your machine and then Enroll MOK (your key) and then reboot again. When you log back in, you will be good to go!**

```bash
mokutil --test-key VMWARE17.der
```
