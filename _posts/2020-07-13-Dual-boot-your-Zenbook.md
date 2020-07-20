---
layout: post
title: "Dual boot your Zenbook with Windows and Ubuntu"
published: false
---

Hello readers, this post is gonna be about dual booting your Asus Zenbook with Windows and Ubuntu. I am writing this since there weren't many articles regarding this and also, I had to spend around 3 to 4 hours. This article might save your time and get your hands less dirty.(Assuming that you have a little experience in dual booting)

I recently bought [Asus Zenbook UX430UAR][link]. Since I use both Linux and windows, I wanted to dual boot my laptop.

Since there are some pre-installed junk softwares in windows, I wanted to do a fresh boot.

First things first, * disable Bitlocker *. Since you are gonna make changes in bios, you have to turn off bitlocker.
To diable bitlocker, open Wndow's powershell as admin and run the following command

    manage-bde -off C:

To check the status, run-

    manage-bde -status C:

Check again after a minute or so and you can see that percentage encrypted is 0.0%.

Now follow along.

1. Make your USB stick bootable with windows(8GB and above is preferred). You can refer about it [here][windows]
2. I had allotted around 50GB for windows, you can do according to your requirements. Installing windows won’t take you much time. The installation process is there in the link mentioned in step-1.
3. Now login to Windows.
4. Next, download the latest LTS version of ubuntu from [here][ubuntu].
5. To make your pendrive bootable, format it first and then  download linuxlive from [here][linuxlive].
6. After you finish installing linuxlive,
    - open it and select your pendrive,
    - choose the ubuntu iso file
    - Tick the `format the key in FAT32 checkbox
    - Now click the lightning icon.
7. After a few minutes your linuxlive key will be ready.
8. Now you can safely insert your bootable pendrive and restart your system and click esc key till the boot menu appears, choose ubuntu.
9. Now you can install ubuntu as you would normally do.






[link]: https://www.google.com/aclk?sa=L&ai=DChcSEwjZ2J6Kp9zqAhUKJSsKHalxBDAYABAEGgJzZg&sig=AOD64_2l4wRdsiG035zYSx4kheO_JGi5Tw&ctype=5&q=&ved=2ahUKEwjkgZiKp9zqAhW_zDgGHfCFAdAQ9aACegQIDhA4&adurl=

[windows]: https://support.microsoft.com/en-in/help/4028192/windows-create-an-iso-file-for-windows-10

[ubuntu]: https://ubuntu.com/download/desktop

[linuxlive]: https://www.linuxliveusb.com/