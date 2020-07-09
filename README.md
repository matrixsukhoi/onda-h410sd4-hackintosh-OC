# onda-h410sd4-hackintosh-OC

10.15.5 10500 UHD630 RTL8168

主要参考了两位大佬的acpi配置与config.plist以及opencore guide

Based on two dalao's works and opencore guide.

[gakaki/ASRock-H410M-ITX-OSX-Hackintosh](https://github.com/gakaki/ASRock-H410M-ITX-OSX-Hackintosh)

[Poilk/H410M-ITX-ac_hackintosh_OC](https://github.com/Poilk/H410M-ITX-ac_hackintosh_OC)

[opencore guide](https://dortania.github.io/OpenCore-Desktop-Guide/config.plist/comet-lake.html)

## Machine

My itx machine:

CPU: Intel i5 10500

--- ok

Board: onda H410sd4

--- ok

Graphic: Intel UHD 630

--- ok

NIC: Realtek RTL8168

--- ok

**Audio: ALC 662 Rev 3**

--- **not functional**, layout id 5,7,11 had been tested. As an alternative, I'm using an externel USB sound card.

**Wireless: No**

USB Ports:

--- basically ok, except the second rear USB port.

Sleep/wakeup:

--- ok

The audio codec is extracted as [codecalc662_0](./codecalc662_0). 

**I'm not sure how to make the on-board audio work correctly. I would appreciate it if someone can help.**

## Bios setup

onda H410sd4 uses AMI BIOS.

***Disable***
1. Fast Boot
2. Secure Boot
3. CSM
4. VT-d
5. Intel SGX
6. Intel Platform Trust
7. CFG-Lock

***Enable***

1. VT-x
2. Above 4G assignment
3. Hyper-Threading
4. EHCI/XHCI Hand-off
5. DVMT Pre-Allocated(iGPU Memory): 64MB

## Possible Problem

1. IOUSB deferred: do not insert the USB-stick on the second rear USB port, just try another.
2. Hdmi externel screen wrong color space (pink screen): To fix it, use [one-key-hidpi](https://github.com/xzhih/one-key-hidpi) inject EDID.

## changelog

- support sleep/wakeup by adding *igfxonln=1* in boot-args
...

~~要不是家里小姐姐喜欢macos的界面，我才不想整辣鸡苹果呢。Fedora不香吗?~~
