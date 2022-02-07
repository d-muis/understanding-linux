# Understanding Linux - Power User's Baby Steps

Or everything I wish I had known when I switched to Linux, as a Windows power user.

## Introduction

This is a comprehensive guide to understanding GNU/Linux systems, learning about their structure, elements, distributions, common jargon etc. It is intended for beginners and intermediate Linux users that wish to understand their system and become power users. This guide will provide a general overview of concepts to give you the best possible start in the shortest amount of time. This guide won't cover very advanced topics that I dare say most Linux power users don't know about or will ever need, such as the inner workings of the kernel, graphics or audio stack, it's a power user's baby steps guide, not a book for developers after all. I recommend reading this after installing your first linux distribution to be able to test everything first-hand.

## The Lore

UNIX was an Operating System (OS) originally created by AT&T which split and evolved over the years. Nowadays there is no single UNIX system, instead it became a specification that many systems follow. Some modern Unix-like systems (also called \*nix) include: FreeBSD, MacOS and GNU/Linux.

POSIX is a specification that many crucial components of \*nix systems follow to allow for compatibility, you will often see software described as POSIX-compliant or mostly POSIX-compliant.

Early UNIX systems were proprietary and did not respect their users freedom. This is why Richard Stallman created GNU (GNU's Not Unix) - a Unix-like OS, which was entirely free to run, study, modify and redistribute. Those four freedoms are guaranteed by the GNU General Public License (GPL) and form the basis of Free and Open Source Software (FOSS). 

The GNU system was missing a solid kernel until Linus Torvalds finally released Linux and so GNU/Linux - a functional free and open source operating system was born. Nowadays many refer to this system just by its kernel's name - Linux. 

While some variants of the BSD system (derived from the original UNIX), such as MacOS remain proprietary, others such as FreeBSD also became open source and provide some benefits over Linux. Still, the latter is by far the favourite of the FOSS community, largely due to its legacy and compatibility.

## The Operating System

Any Unix-like system consists of those four main components: kernel, shell, programs and filesystem.

#### Kernel

The kernel directly interacts with computer's hardware. It allocates time and memory, handles files and processes. You don't need to worry about how it does it, none of us know. The Linux kernel is able to dynamically load modules and can also be given parameters to modify its functionality. Aside from the default kernel, others also exist, such as the Long Time Support (LTS) kernel.

#### Shell

The shell is a program that allows the user to interact with the system, it sends direct requests to the kernel. Most systems consist of multiple shells: a system shell, a user shell and a graphical shell. The system shell can be interacted with using a programming language - the Bourne Shell (sh) or its modern mostly POSIX-compliant derivatives like the Bourne-Again Shell (bash). The user shell doesn't need to be POSIX-compliant at all and can include many convenience features, the Z shell (zsh) is a popular choice. System and user shells are interacted with through Command Line Interface - CLI. The Graphical User Interface (GUI) which lets you open applications or move files with your mouse is a graphical shell.

#### Programs

Many commands = programs

#### Filesystem

Directory tree
Everything is a file

## Distributions

## Resources

UNIX:
http://www.ee.surrey.ac.uk/Teaching/Unix/unixintro.html
https://www.tutorialspoint.com/unix/unix-getting-started.html

Linux Kernel:
https://linuxhint.com/linux-kernel-tutorial-beginners/
https://wiki.archlinux.org/title/Kernel_module
