---
layout: post
title: A tips for modify linux(virtual machine) any user’s login password when you didn’t known the root password
date: 2014-09-14 22:14:55
---

    Author:Demon@FF0000 Team

Yestoday, I found a question about how to modify my vm’s ubuntu login password, Our company’s partner(id:rains) tell me a tips to deal with it. so i just record it and want to help somebody:)

##### scenario:

One day you open your VM linux system, Found need to login, But you forgot your password, so, is this have some way to login as root user?

##### method:

First, you should prepare a linux iso mirror, In there , I download ubuntu.iso, size is 1.4G. and then,you can start reset your root password. select vm options, Load your .iso file as CD/ROM, and reboot your system,  select CD/ROM to start, and then, you will see the iso was started, Just like reinstall system, and look for ubuntu try. In the menu you can see that option, Click it, So you will enter a temp system, It’s needn’t password, And it’s independent. Next , open Terminal, And start to modify password.

Because your system was independented, so you should find it. In general, It’s in /dev/sda1, or sda2,  it’s up to your system  environment.

Next , mount it , On Terminal, type this command:

mount /dev/sda1 /mnt/   it’s means mount your old system directory.

Then , use chroot to change root directory. type:

chroot /mnt,  And then , cd /mnt , use passwd root to change your root password,  At this time ,you was a root permission, so you can change any user’s password, when it prompt success, you can shutdown this temp system , close CD/ROM startup,  Pop-up your iso file , then you can use your new password to login your linux system:)
