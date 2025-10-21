+++
date = '2025-10-21T17:08:24+01:00'
draft = true
title = 'Using ventoy to bypass secure boot'
+++

## Intro

My laptop is a [Acer Aspire Vero AV14](https://business.currys.co.uk/catalogue/computing/laptops/windows-laptop/acer-aspire-vero-av14-52p-14-laptop-intel-core-i5-512-gb-ssd-blue/N853644W), it serves me well and is very powerful.
However recently Acer have locked my bios after I repeatedly changed my OS from Windows to Linux.I am completely unable to access the boot menu/bios settings as it prompts me to enter a password, I tried the usual solution of resetting the bios by removing the CMOS however it isn't removable and I can't find it on the board.

I researched online about Acer backup codes and it led me to [this site](https://www.biosbug.com/acer/). It instructed me to press enter on the password screen 3 times and a code will show up, this code can be used to figure out the password and get back into the bios.However on my model, this is completely removed and no code appears. I noticed that a text file with an encrypted string would appear on any USB device I connected when I did this process.

So I contacted Acer support and they told me to send them my laptop and I would have to pay for it... Absolutely not!!! I will not pay for a problem not caused by me on a otherwise functioning device. So I was stuck with Operating Systems that supported secure boot automatically in both the installer and the OS, I had to make a choice between [Fedora](https://fedoraproject.org/) or [Debian](https://www.debian.org/). I went with Fedora because it had more up-to-date packages at the time and I was also interested in running [Hyprland](https://github.com/hyprwm/Hyprland) because It's the first WM I used and the one I continue to use on my [Arch](https://archlinux.org/) desktop. However the support for Hyprland wasn't great so I settled with using [Sway](https://swaywm.org/).

I used Fedora for around 5 months and it worked perfectly fine, however I really wanted to use Arch. The reason I didn't use Arch from the start is because it's installer didn't support secure boot, I tried to use [Archboot](https://archboot.com/) but that didn't work either. I accepted the fact that I couldn't run Arch until, I was using my [Ventoy](https://www.ventoy.net/en/index.html) (USB intallation image that supports multiple isos at once) to install OpenBSD onto my server when I discovered an option to "Search and boot BOOTX64.efi". This file begins the boot process of Linux booting into the systems boot manager, this is when I released I could use Ventoy as a way to bypass secure boot.

## The process

{{$image := resources.Get "images/partition_config.png"}}
