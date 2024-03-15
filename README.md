```
wget -O 1.iso https://mirror.rackspace.com/archlinux/iso/2024.03.01/archlinux-2024.03.01-x86_64.iso
```
```
wget -O ngrok.tgz https://bin.equinox.io/c/bNyj1mQVY4c/ngrok-v3-stable-linux-amd64.tgz
```
```
tar -xf ngrok.tgz
```
```
rm -rf ngrok.tgz
```
```
./ngrok config add-authtoken 2dFqRy2j3dJ6qAwES1m4z16SQ6u_3RdeXyoGkEh6TwTW5LUG8
```
```
./ngrok tcp 5900
```
```
sudo apt update && sudo apt upgrade && sudo apt install qemu-kvm
```
```
qemu-img create -f raw 1.img 32G
```
```
sudo qemu-system-x86_64 -m 8G -cpu host -boot order=c -drive file=1.iso,media=cdrom -drive file=1.img,format=raw -device usb-ehci,id=usb,bus=pci.0,addr=0x4 -device usb-tablet -vnc :0 -smp cores=2 -device rtl8139,netdev=n0 -netdev user,id=n0 -vga qxl -enable-kvm
```
