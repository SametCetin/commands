# KVM Notlar



virsh shutdown <makine-adi>. 
virsh start <makine-adi>. 

## cd mount komutları
virsh change-media vm_tcat2 sdb --eject --live --config. 

## vnc port sorgula
virsh vncdisplay <makine-adi>. 

## çalışan makineler
virsh list --all. 

## vnc server - localhost tünel
ssh -L 5900:localhost:5900 <sanal-makine-adi>. 

## kurulum komutu
```bash
sudo virt-install \
  --name vm_tcat2 \
  --ram 2048 \
  --vcpus 2 \
  --cpu host-passthrough \
  --os-variant win10 \
  --arch i686 \
  --disk path=/data/vm_tcat2/vm_tcat2.qcow2,format=qcow2,bus=sata,size=40 \
  --cdrom /data/installs/win10_ent_ltsc_2021_x86.iso \
  --network network=default,model=e1000 \
  --graphics vnc,listen=127.0.0.1 \
  --noautoconsole
```