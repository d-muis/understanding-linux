# Understanding Linux

Power User's Baby Steps, or everything I wish I had known when I switched to Linux, as a Windows power user.

## Introduction

This is a comprehensive guide to understanding GNU/Linux systems, learning about their origin, structure, components, distributions, common jargon etc. It is intended for beginners and those who wish to understand their system and eventually become "power users". This guide provides a general overview of concepts to give you the best possible start in the shortest amount of time. It won't make you an expert or teach you everything in detail but it can point you in the right direction, clarify confusions, get you well equipped to expand your knowledge on more specific topics. I highly recommend reading this after installing your first linux distribution (any of them will do) to be able to test everything first-hand.

## Lore

**UNIX** was an Operating System (OS) originally created by AT&T which split and evolved over the years. Nowadays there is no single UNIX system, instead it became a specification that many systems follow. Some modern Unix-like systems (also called \*nix) include: BSD, MacOS and GNU/Linux. **POSIX** is a specification that many crucial components of \*nix systems follow to allow for interoperability. You will often see software described as POSIX-compliant or mostly POSIX-compliant.

Early UNIX systems were proprietary and did not respect their users freedom (proprietary meaning closed-source, copyrighted). This is why **Richard Stallman** created GNU (recursive acronym for "GNU's Not Unix") - a Unix-like OS, which was entirely free to run, study, modify and redistribute. Those four freedoms are guaranteed by the GNU General Public License (GPL) and form the basis of Free and Open Source Software (FOSS). The GNU system was incomplete until **Linus Torvalds** finally released the Linux kernel and so **GNU/Linux** - a fully functional free and open source operating system was born. Nowadays many refer to it as just Linux (Linux Is Not UniX).

**BSD** (Berkeley Software Distribution) was a proprietary OS which derives from the original UNIX. FreeBSD and OpenBSD are its FOSS derivatives while MacOS is a proprietary one. They follow similar specifications as Linux and many of their components are relatively interchangeable.

## Distributions

Linux is completely modular: its elemenets can be swapped, added or removed, tailored to the purpose of the system or one's preferences. This is exactly what distributions do - released by communities or companies, they combine all necessary components of the operating system with regard to its intended use case, and publish, or **distribute** it for us to use. Some **distros** aim to be very minimal, intended for advanced users or servers, others provide a user friendly alternative to Windows or Mac. Most of the crucial components are identical across all of them and most of the differences are purely visual and can be changed in a matter of minutes. For an advanced user, few factors are really important that differ between the distributions - mainly their release model and package manager. Distribution "families" are big groups of distributions based on a single descendant and generally share their release model and packaging format. While there are countless distributions out there, there's only a handful of meaningful distribution "families". The most popular distribution families for desktop use include: **Debian**, **Ubuntu** (which itself is a Debian derivative), **Fedora**, **SUSE** and **Arch**. There are also some more unique or usecase-specific distributions like **Android** for mobile phones, **Red Hat Enterprise Linux** for enterprise/servers etc. You can look at the detailed distribution tree [here](https://upload.wikimedia.org/wikipedia/commons/8/8c/Linux_Distribution_Timeline_Dec._2020.svg) but don't worry about it too much.

#### Release Models

- **Point release** distributions release updates at set time intervals, e.g. once/twice a year. In this model, software versions are fixed in place over a single release cycle (rather than being updated continuously). Point release distros often have multiple supported versions/releases, similarily to MacOS or Windows. This release model prioritizes stability but depending on the frequency of updates, software might quickly become "outdated". It also reduces the required system maintenance and is therefore considered ideal for servers or casual desktop users. Point release distributions include Debian, Ubuntu, RHEL, OpenSUSE Leap.

- **Rolling release** distributions, on the other hand, continuously release updates to programs as they become available. Rolling release distros only have a single supported version/release - it changes continuously (hence rolling) and users need to keep up with it by performing frequent updates. This release model is generally viewed as more advanced and it prioritizes keeping all software up to date. Rolling release distros usually require more user involvement/maintenance. Notable examples of rolling release distros include Arch, Manjaro, OpenSUSE Tumbleweed, Gentoo.

- **Hybrid** or **semi-rolling** release, is a model that incorporates the inherent stability of point-release with access to latest software provided by rolling release. There are different variations of this model, but it is usually achieved by freezing a lot of crucial system packages, while providing continuous updates to e.g. the desktop and some applications. Some distributions go a step further and even provide kernel or graphics driver updates, in order to accomodate new hardware or support some new software. Hybrid or semi-rolling distributions include Linux Mint, KDE Neon (both based on Ubuntu) and Fedora.

Most major distributions have a single main release model, but many also offer alternatives. For example, Debian is point-release by default and releases a new version around every 2 years or so. In addition, it has two rolling release branches - testing and unstable (sid). Those braches are meant for testing and development, not for end users, but technically nothing is stopping you from using them as such. Distributions such as OpenSUSE have two primary models - a point-release "Leap" and rolling "Tumbleweed". Relase model aside, most distributions release security updates in a rolling fashion, in order to make sure any vulnerabilities are immediately addressed.

#### Packages and Package Managers

**Packages** are just software, "packaged" into archives that preserve their directory structure and can include some metadata (additional information) for a package manager to install them. There are different ways to package software, determined by the packaging format. 
**Package managers** are programs used by distributions to manage downloading and installing packages from the official repositories, so called **repos** (collections of packages, stored on a server). 
Package managers are meant to work with specific **packaging formats**. The availability of certain packages might vary between the existing formats but practically speaking this is rarely an issue due to the active community.

The most noteable packaging formats and their corresponding package managers are:
- Debian-based distros (Ubuntu, Mint etc.) share a packaging format called .deb, managed by the **APT** package manager.
- Red Hat family distros (eg. Fedora) use the .rpm package format and manage their packages using **DNF**.
- SUSE also uses .rpm packages but manages them using **ZYpp**.
- Arch-based distros use **pacman** to manage .pkg.tar.zst packages, which are simply compressed archives.

#### Package Dependencies 

When writing software, developers rely on code or programs writtern by others before them. Developers may choose to include this code inside of their software (called **static linking**), or exclude it but require the program to be present on the operating system for their software to function (**dynamic linking**). On Linux, dynamic linking is often preferred, because it reduces disk space usage and allows for independent security updates to be performed. **Dependencies** are such programs (or "packages") that are required for another program to run. Whenever you install a package, package managers perform "dependency resolution" and automatically download and install all the required dependencies. When a package has been installed as a dependency but is no longer required (i.e. the program that depended on it had been removed), the package is called an **orpahn** and can be safely removed using the package manager. 

#### Universal Packaging Formats

Aside from default system packages, there exist supplementary packaging formats which can be used to install and update applications irrespective of the distributions' release models. Thanks to those formats, users of point release distros can keep most of their apps up to date, while not having to update their entire system - the best of both worlds. The main universal packaging formats are: 
- **Flatpak**
- **Snap**
- **AppImage**
- **nix**
  
Some of those packaging formats (AppImage) bundle all the required dependencies together with the software to make it as portable as possible, at the cost of large file size and slow security updates. Others (Flatpak) offer runtimes - dependency groups that allow many dependencies to be shared. Some (nix) are essentially distribution-agnostic package managers, separate from the OS. For most users, Flatpaks are the recommended format to use for applications on most distributions, other than Ubuntu which ships Snaps by default.

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
