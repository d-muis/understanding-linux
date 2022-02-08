# Understanding Linux

Power User's Baby Steps, or everything I wish I had known when I switched to Linux, as a Windows power user.

## Introduction

This is a comprehensive guide to understanding GNU/Linux systems, learning about their origin, structure, elements, distributions, common jargon etc. It is intended for beginners and intermediate Linux users that wish to understand their system and become power users. This guide provides a general overview of concepts to give you the best possible start in the shortest amount of time. This guide won't cover very advanced topics that I dare say most Linux power users don't know about or will ever need, such as the inner workings of the kernel or the graphics stack, it's a power user's baby steps guide, not a book for kernel developers. I highly recommend reading this after installing your first linux distribution (any of them will do!) to be able to test everything first-hand.

## Background

UNIX was an Operating System (OS) originally created by AT&T which split and evolved over the years. Nowadays there is no single UNIX system, instead it became a specification that many systems follow. Some modern Unix-like systems (also called \*nix) include: FreeBSD, MacOS and GNU/Linux.

POSIX is a specification that many crucial components of \*nix systems follow to allow for interoperability. You will often see software described as POSIX-compliant or mostly POSIX-compliant.

Early UNIX systems were proprietary and did not respect their users freedom. This is why Richard Stallman created GNU (GNU's Not Unix) - a Unix-like OS, which was entirely free to run, study, modify and redistribute. Those four freedoms are guaranteed by the GNU General Public License (GPL) and form the basis of Free and Open Source Software (FOSS). 

The GNU system was incomplete until Linus Torvalds finally released the Linux kernel and so GNU/Linux - a fully functional free and open source operating system was born. Nowadays many refer to it as just Linux (Linux Is Not UniX - we love recursive acronyms).

BSD (Berkeley Software Distribution) was a proprietary OS which derives from the original UNIX. FreeBSD and OpenBSD are its FOSS derivatives while MacOS is a proprietary one. They use different kernels but follow similar specifications as GNU/Linux and many of their components are interchangeable.

## Distributions

Unix-like systems are completely modular. Their elemenets can be switched, added or removed depending on the purpose of the system or one's preferences. This is exactly what distributions do, released by communities or companies, they combine all necessary components of the operating system with regard to its intended use case. Some "distros" aim to be very minimal, intended for advanced users or servers, others provide a user friendly alternative to Windows or Mac. Most of the crucial components are identical across all of them and most of the differences are purely visual and can be changed in a matter of minutes. For an advanced user, only few factors are really important that differ between the distributions - their release model and their package manager. Distribution families are big groups of distributions based on a single descendant and generally share their release model and packaging format

#### Release Models

Distributions release software updates using either a point release or rolling release model. Point release distros utilize whole system updates that occur at set intervals. This release model prioritizes stability but depending on the frequency of updates, software might quickly become out of date. Point release distros can have many different versions, similarily to MacOS or Windows. Rolling release distributions, on the other hand, continuously release updates to specific programs rather than the entire system. This release model, often called "bleeding edge", is generally viewed as more advanced and it prioritizes keeping all software up to date while. Rolling release distros are not unstable but their maintenance might require more user involvement.

Debian and Red Hat distribution families are mostly point release and include popular distributions such as Ubuntu, Mint or Fedora. Arch and Gentoo distributions and their families are rolling release, this includes Manjaro or ChromeOS. The OpenSUSE distribution provides both release models to choose from.

#### Packages

Packages are just software

Package managers are programs used by distributions to manage downloading and installing software, called packages, from the official servers, called repositories or repos. Package managers are meant to work with specific packaging formats, the availability of certain packages might vary between the existing formats but practically speaking this is rarely an issue due to the active community.

The most noteable packaging formats and their corresponding package managers are:

Debian-based distros (Ubuntu, Mint etc.) share a packaging format called .deb, managed by the APT package manager. Red Hat family distros (eg. Fedora) use the .rpm package format and manage their packages using DNF. SUSE also uses .rpm packages but manages them using ZYpp. Arch-based distros use pacman to manage .pkg.tar.zst packages, which are simply compressed archives.

#### Universal Packages

Appimages, flatpaks, snaps - containerized applications

## UNIX basics

Before learning anything else, you should know the general structure of the system as well as its main components. 
Any Unix-like system consists of the following basic components: kernel, shell, programs and the filesystem. More detailed components such as an init system or a bootloader can be specified depending on their exact function or structure, I will talk about those later.

#### Kernel

The kernel directly interacts with computer's hardware. It allocates time and memory, handles files and processes. You don't need to worry about how it does it, none of us know. The Linux kernel is able to dynamically load modules and can also be given parameters that modify its functionality. Aside from the default kernel, others also exist, such as the Long Term Support (LTS) kernel.

#### Shell

The shell is a program that allows the user to interact with the system, it sends direct requests to the kernel. Most systems consist of multiple shells: a system shell, a user shell and a graphical shell. Bourne Shell (sh) or its derivatives like the Bourne-Again Shell (bash) are most commonly used as the system shell. The user shell often includes convenience features and unlike the system shell, doesn't need to be POSIX-compliant. System and user shells are programming language interpreters, interacted with through Command Line Interface (CLI) of a program called the Terminal. The Graphical User Interface (GUI) which lets you open desktop applications or move files with your mouse is a graphical shell.

#### Files

Most commands aren't actually a part of the shell scripting language. Instead, they are small programs stored on your system as executable files. The other type of commands are shell builtin functions, stored directly in the shell. The shell itself is also a program, an executable file. In fact, even the kernel itself is a file. This is because in Unix-like systems, everything is a file (or to be precise, a file descriptor). 

Directories or "folders", are a special kind of files able to store other files, they're the building blocks of the filesystem. Symbolic Link files are "shortcuts" that point to a different file. Block Device files represent physical hardware, input/output devices such as hard drives or printers. There's even more special file types but for now just remember dirs and symlinks.

#### Filesystem

The filesystem is simply a tree-like structure of directories. At the very base of it is the / directory, called root. The / directory consists of many other directories and their subdirectories that store files depending on their function. This directory is similar to C:\ on Windows but unlike on Windows, if you connect a second drive to your computer, it will appear as a file inside your filesystem, rather than a separate drive outside of /. If this sounds confusing, don't worry, this will be covered in detail later but it's important that you first understand the concept of a tree-like directory structure.

## Good Resources

UNIX:
http://www.ee.surrey.ac.uk/Teaching/Unix/unixintro.html
https://www.tutorialspoint.com/unix/unix-getting-started.html

Linux Kernel:
https://linuxhint.com/linux-kernel-tutorial-beginners/
https://wiki.archlinux.org/title/Kernel_module

Filesystem:
https://www.youtube.com/watch?v=dDwXnB6XeiA
https://www.youtube.com/watch?v=WWvsDFOhiQY
