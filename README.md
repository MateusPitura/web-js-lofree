<h1 align="center"> 
  <p>Lofree Control Hub Web Replica</p> 
  <img src="https://github.com/user-attachments/assets/0af50011-ca26-477f-a15b-2f115750929c" width="75%"> 
</h1> 

<p> 
  <img src="https://img.shields.io/badge/Release-Oct%202026-green">  
  <img src="https://img.shields.io/github/stars/MateusPitura/web-js-lofree?style=social"> 
</p>  

## Description

This is a independent replica of the Lofree Control Hub Web, a web application that allows users to control their Lofree devices. The [original site](https://url.mateuspitura.com?q=lofree.tech/keyboard) is hosted in Hong Kong, which can result in slow loading times for users in other regions, and it may become unavailable if the maintainer takes it down in the future. This project aims to provide a faster-loading alternative and serve as a backup of the original site

The original site files were downloaded manually, with only minor changes made to ensure they work, such as removing redirects to the original domain and enabling test mode. The main JavaScript code was downloaded in minified form and formatted using Prettier. The site was tested with a Lofree Flow Lite 84, so some assets may not be available with other devices

- [Features](#features)
- [How to Run](#how-to-run)
- [Technologies Used](#technologies-used)
- [Authors](#authors)

## Features

- ⚡ **Faster loading:** hosted in GitHub Pages, which use CDN to serve files quickly
- 💾 **Backup copy:** preserves a usable copy
- 🎨 **Frontend only:** the app runs in the browser

## How to Run

Visit [https://lofree.mateuspitura.com/](https://url.mateuspitura.com?q=lofree.mateuspitura.com) and connect your keyboard over cable or 2.4GHz receiver

### Troubleshooting

**The page stays on infinite loading in Ubuntu 24.04:**

```bash
sudo nano /etc/udev/rules.d/70-lofree-hid.rules
```

Add this:

```udev
KERNEL=="hidraw*", SUBSYSTEM=="hidraw", ATTRS{idVendor}=="05ac", ATTRS{idProduct}=="024f", TAG+="uaccess"
```

> [!WARNING]
> The idVendor and idProduct can vary

```bash
sudo udevadm control --reload-rules
sudo udevadm trigger --subsystem-match=hidraw
```

**Fn keys do not work, even when Fn is pressed in Ubuntu 24.04:**

```bash
echo 2 | sudo tee /sys/module/hid_apple/parameters/fnmode
echo "options hid_apple fnmode=2" | sudo tee /etc/modprobe.d/20_lofree_fn_mode_fix.conf
```

## Technologies Used

<!--Link for badges: https://github.com/Ileriayo/markdown-badges -->

<p align="left">
	<img src="https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E" alt="JavaScript"/>
</p> 

## Authors 

| Mateus Pitura | 
|------|
| <p align="center"><img src="https://avatars.githubusercontent.com/u/119008106" width="100" height="100"></p> |  
| <a href="https://url.mateuspitura.com?q=linkedin.com/in/mateuspitura/"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&goColor=white"> |
