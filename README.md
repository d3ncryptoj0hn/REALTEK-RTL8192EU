# REALTEK-RTL8192EU
Realtek driver support tenda wireless adaptor

## Tenda Wireless Wifi driver

## Install Dependencies

```
sudo apt list linux-headers-generic build-essential dkms git
```
Install if necessary:
```
sudo apt -y install linux-headers-generic build-essential dkms git
```

## install


```
sudo rmmod 8192eu
sudo rmmod rtl8xxxu
sudo dkms remove -m rtl8192eu -v 1.0
```

Blacklist driver (rtl8xxxu on Kali/Ubuntu):

```
sudo -i
echo "blacklist rtl8xxxu" >> /etc/modprobe.d/blacklist-rtl8xxxu.conf
echo "blacklist rtl8xxxu" >> /etc/modprobe.d/rtl8xxxu.conf
```

```
sudo cp -ar . /usr/src/rtl8192eu-1.0
sudo dkms add -m rtl8192eu -v 1.0
sudo dkms install -m rtl8192eu -v 1.0
```

## USE MAKE

```
sudo make clean
sudo make
sudo make install
sudo modprobe 8192eu
```

### Done!
