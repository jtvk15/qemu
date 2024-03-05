```
wget -O win11.iso "https://software.download.prss.microsoft.com/dbazure/Win11_23H2_Chinese_Simplified_x64.iso?t=8619439a-4186-499d-a368-5781ba869761&e=1701868678&h=5f0d412168b6405bc82ad58fdc0b7b5220db81226571cb10412978d24b764bb1"
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
./ngrok config add-authtoken 2Z7oSMlocSVlB0YQqch4VPjvMFr_3nh2SW7Cx6zYpCqEHN6XQ
```
```
./ngrok tcp 5900
```
```
apt update && apt install qemu-kvm
```
```
qemu-img create -f raw win11.img 100G
```
```
qemu-system-x86_64 -m 8G -cpu host -boot order=c -drive file=win11.iso,media=cdrom -drive file=win11.img,format=raw -device usb-ehci,id=usb,bus=pci.0,addr=0x4 -device usb-tablet -vnc :0 -smp cores=2 -device rtl8139,netdev=n0 -netdev user,id=n0 -vga qxl -enable-kvm
```
