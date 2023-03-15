
You Got a Package

In this lab, you will learn how to manage software applications on
your Linux system. You will learn how to use the Debian package manager
to download, install, remove, search, and update software packages.


How to download packages
========================


As the [root] user, change to the [/tmp] directory:

``` 
root@ubuntu-linux:~# cd /tmp
```

To download the [cmatrix] package, you can run the command:

``` 
root@ubuntu-linux:/tmp# apt-get download cmatrix
Get:1 http://ca.archive.ubuntu.com/ubuntu bionic/universe amd64 cmatrix amd64
1.2a-5build3 [16.1 kB]
Fetched 16.1 kB in 1s (32.1 kB/s)

```

The [cmatrix] package will be downloaded in [/tmp]:

``` 
root@ubuntu-linux:/tmp# ls 

cmatrix_2.0-2_amd64.deb
```

Notice the [.deb] extension in the package name, which signals
that it\'s a Debian package. On RedHat distributions, package names end
with the [.rpm] extension. You can list the files inside the
[cmatrix] package by running the command [dpkg -c] as
follows:

**Note:** Please update package name in below command incase you get different version.

``` 
root@ubuntu-linux:/tmp# dpkg -c cmatrix_2.0-2_amd64.deb

drwxr-xr-x root/root         0 2019-07-09 19:01 ./
drwxr-xr-x root/root         0 2019-07-09 19:01 ./usr/
drwxr-xr-x root/root         0 2019-07-09 19:01 ./usr/bin/
-rwxr-xr-x root/root     22680 2019-07-09 19:01 ./usr/bin/cmatrix
drwxr-xr-x root/root         0 2019-07-09 19:01 ./usr/share/
drwxr-xr-x root/root         0 2019-07-09 19:01 ./usr/share/applications/
-rw-r--r-- root/root       241 2019-05-07 16:12 ./usr/share/applications/cmatrix.desktop
drwxr-xr-x root/root         0 2019-07-09 19:01 ./usr/share/consolefonts/
-rw-r--r-- root/root      4096 2019-03-27 14:36 ./usr/share/consolefonts/matrix.fnt
-rw-r--r-- root/root      1727 2019-07-09 19:01 ./usr/share/consolefonts/matrix.psf.gz
drwxr-xr-x root/root         0 2019-07-09 19:01 ./usr/share/doc/
drwxr-xr-x root/root         0 2019-07-09 19:01 ./usr/share/doc/cmatrix/
-rw-r--r-- root/root        65 2019-03-27 14:36 ./usr/share/doc/cmatrix/README
-rw-r--r-- root/root      3221 2019-03-27 14:36 ./usr/share/doc/cmatrix/README.md
-rw-r--r-- root/root      1730 2019-07-09 19:01 ./usr/share/doc/cmatrix/changelog.Debian.gz
-rw-r--r-- root/root      1109 2019-05-07 16:12 ./usr/share/doc/cmatrix/copyright
drwxr-xr-x root/root         0 2019-07-09 19:01 ./usr/share/man/
drwxr-xr-x root/root         0 2019-07-09 19:01 ./usr/share/man/man1/
-rw-r--r-- root/root       877 2019-07-09 19:01 ./usr/share/man/man1/cmatrix.1.gz
```

Notice that we only downloaded the package, but we didn't install it
yet. Nothing will happen if you run the [cmatrix] command:

``` 
root@ubuntu-linux:/tmp# cmatrix
bash: /usr/bin/cmatrix: No such file or directory
```


How to install packages
=======================


You can use the [-i] option with the [dpkg] command to
install a downloaded package:

``` 
root@ubuntu-linux:/tmp# dpkg -i cmatrix_2.0-2_amd64.deb
Selecting previously unselected package cmatrix.
(Reading database ... 178209 files and directories currently installed.) Preparing to unpack cmatrix_2.0-2_amd64.deb...
Unpacking cmatrix (1.2a-5build3) ... 
Setting up cmatrix (1.2a-5build3) ...
Processing triggers for man-db (2.8.3-2ubuntu0.1) ... 
root@ubuntu-linux:/tmp#
```

And that\'s it! Now run the [cmatrix] command:

``` 
root@ubuntu-linux:/tmp# cmatrix
```

You will see the matrix running on your terminal like in the following
image:


![](./images/a6f7e7c8-6eee-485b-876b-3addebdcb0ab.png)





We have taken the long way to install the [cmatrix] package. We
first downloaded the package, and then we installed it. You can install
a package right away (without downloading it) by running the command
[apt-get install] followed by the package name:

``` 
apt-get install package_name
```

For example, you can install the **GNOME Chess** game by running the
command:

``` 
root@ubuntu-linux:/tmp# apt-get install gnome-chess 
Reading package lists... Done
Building dependency tree
Reading state information... Done 
Suggested packages:
  bbchess crafty fairymax fruit glaurung gnuchess phalanx sjeng stockfish toga2 
The following NEW packages will be installed:
  gnome-chess
0 upgraded, 1 newly installed, 0 to remove and 357 not upgraded. 
Need to get 0 B/1,514 kB of archives.
After this operation, 4,407 kB of additional disk space will be used. 
Selecting previously unselected package gnome-chess.
(Reading database ... 178235 files and directories currently installed.) Preparing to unpack .../gnome-chess_1%3a3.28.1-1_amd64.deb ...
Unpacking gnome-chess (1:3.28.1-1) ...
Processing triggers for mime-support (3.60ubuntu1) ...
Processing triggers for desktop-file-utils (0.23-1ubuntu3.18.04.2) ... 
Processing triggers for libglib2.0-0:amd64 (2.56.3-0ubuntu0.18.04.1) ... 
Setting up gnome-chess (1:3.28.1-1) ...
Processing triggers for man-db (2.8.3-2ubuntu0.1) ... 
Processing triggers for gnome-menus (3.13.3-11ubuntu1.1) ... 
Processing triggers for hicolor-icon-theme (0.17-2) ...
```

Now you can start the game by running the [gnome-chess] command:

``` 
root@ubuntu-linux:/tmp# gnome-chess
```


![](./images/0739e34c-67f4-43fd-b8d4-615df8130aa0.png)






How to remove packages
======================


You can easily remove a package by running the command [apt-get
remove] followed by the package name:

``` 
apt-get remove package_name
```

For example, if you are tired of the matrix lifestyle and have decided
to remove the [cmatrix] package, you can run:

``` 
root@ubuntu-linux:/tmp# apt-get remove cmatrix 
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following packages will be REMOVED:
    cmatrix
0 upgraded, 0 newly installed, 1 to remove and 357 not upgraded. 
After this operation, 49.2 kB disk space will be freed.
Do you want to continue? [Y/n] y
(Reading database ... 178525 files and directories currently installed.) 
Removing cmatrix (1.2a-5build3) ...
Processing triggers for man-db (2.8.3-2ubuntu0.1) ...
```

Now, if you run the [cmatrix] command, you will get an error:

``` 
root@ubuntu-linux:/tmp# cmatrix
Command 'cmatrix' not found, but can be installed with: 
apt install cmatrix
```

The [apt-get remove] command removes (uninstalls) a package, but
it doesn't remove the package configuration files. You can use the
[apt-get purge] command to remove a package along with its
configuration files.

For example, if you want to remove the [gnome-chess] package along
with its configuration files, you can run:

``` 
root@ubuntu-linux:/tmp# apt-get purge gnome-chess 
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following package was automatically installed and is no longer required:    
  hoichess
Use 'apt autoremove' to remove it.
The following packages will be REMOVED:
  gnome-chess*
0 upgraded, 0 newly installed, 1 to remove and 357 not upgraded. 
After this operation, 4,407 kB disk space will be freed.
Do you want to continue? [Y/n] y
(Reading database ... 178515 files and directories currently installed.) 
Removing gnome-chess (1:3.28.1-1) ...
Processing triggers for mime-support (3.60ubuntu1) ...
Processing triggers for desktop-file-utils (0.23-1ubuntu3.18.04.2) ... 
Processing triggers for libglib2.0-0:amd64 (2.56.3-0ubuntu0.18.04.1) ... Processing triggers for man-db (2.8.3-2ubuntu0.1) ...
Processing triggers for gnome-menus (3.13.3-11ubuntu1.1) ... 
Processing triggers for hicolor-icon-theme (0.17-2) ...
(Reading database ... 178225 files and directories currently installed.) 
Purging configuration files for gnome-chess (1:3.28.1-1) ...
```

You can even see in the last line in the output it says [Purging
configuration files for gnome-chess (1:3.28.1-1) \...], which
means that the configuration files for [gnome-chess] are being
removed as well.


How to search for packages
==========================

Let's say that you want to install the [wireshark]
package, but you can only remember that the package name has the word
[shark] in it. In this case, you can run the command:

``` 
root@ubuntu-linux:/tmp# apt-cache search shark
dopewars - drug-dealing game set in streets of New York City
dopewars-data - drug-dealing game set in streets of New York City - data files forensics-extra - Forensics Environment - extra console components (metapackage) kernelshark - Utilities for graphically analyzing function tracing in the kernel libcrypto++-dev - General purpose cryptographic library - C++ development libshark-dev - development files for Shark
libshark0 - Shark machine learning library
libwireshark-data - network packet dissection library -- data files 
libwireshark-dev - network packet dissection library -- development files libwireshark10 - network packet dissection library -- shared library 
libwiretap-dev - network packet capture library -- development files
libwsutil-dev - network packet dissection utilities library -- development files libwsutil8 - network packet dissection utilities library -- shared library netmate - netdude clone that shows pcap dump lines in network header style plowshare-modules - plowshare drivers for various file sharing websites
shark-doc - documentation for Shark
tcpxtract - extract files from network traffic based on file signatures 
tshark - network traffic analyzer - console version
wifite - Python script to automate wireless auditing using aircrack-ng tools wireshark - network traffic analyzer - meta-package
wireshark-common - network traffic analyzer - common files 
wireshark-dev - network traffic analyzer - development tools 
wireshark-doc - network traffic analyzer - documentation 
wireshark-gtk - network traffic analyzer - GTK+ version 
wireshark-qt - network traffic analyzer - Qt version
zeitgeist-explorer - GUI application for monitoring and debugging zeitgeist forensics-extra-gui - Forensics Environment - extra GUI components (metapackage) horst - Highly Optimized Radio Scanning Tool
libvirt-wireshark - Wireshark dissector for the libvirt protocol 
libwiretap7 - network packet capture library -- shared library 
libwscodecs1 - network packet dissection codecs library -- shared library minetest-mod-animals - Minetest mod providing animals
nsntrace - perform network trace of a single process by using network namespaces libwireshark11 - network packet dissection library -- shared library 
libwiretap8 - network packet capture library -- shared library
libwscodecs2 - network packet dissection codecs library -- shared library libwsutil9 - network packet dissection utilities library -- shared library
```

And you are bombarded with a massive output that lists all the package
names that have the word [shark] in their package description. I
bet you can spot the package [wireshark] in the middle of the
output. We can get a much shorter and a refined output by using the
[-n] option:

``` 
root@ubuntu-linux:/tmp# apt-cache -n search shark
kernelshark - Utilities for graphically analyzing function tracing in the kernel libshark-dev - development files for Shark
libshark0 - Shark machine learning library
libwireshark-data - network packet dissection library -- data files 
libwireshark-dev - network packet dissection library -- development files
libwireshark10 - network packet dissection library -- shared library 
shark-doc - documentation for Shark
tshark - network traffic analyzer - console version 
wireshark - network traffic analyzer - meta-package 
wireshark-common - network traffic analyzer - common files 
wireshark-dev - network traffic analyzer - development tools 
wireshark-doc - network traffic analyzer - documentation 
wireshark-gtk - network traffic analyzer - GTK+ version 
wireshark-qt - network traffic analyzer - Qt version
libndpi-wireshark - extensible deep packet inspection library - wireshark dissector 

libvirt-wireshark - Wireshark dissector for the libvirt protocol
libwireshark11 - network packet dissection library -- shared library
```

This will only list the packages that have the word [shark] in
their package names. Now, you can install [wireshark] by running
the command:

``` 
root@ubuntu-linux:/tmp# apt-get install wireshark
```


How to show package information
===============================


To view package information, you can use the command [apt-cache
show] followed by the package name:

``` 
apt-cache show package_name
```

For example, to display the [cmatrix] package information, you can
run:

``` 
root@ubuntu-linux:~# apt-cache show cmatrix 
Package: cmatrix
Architecture: amd64 
Version: 1.2a-5build3 
Priority: optional 
Section: universe/misc 
Origin: Ubuntu
Maintainer: Ubuntu Developers <ubuntu-devel-discuss@lists.ubuntu.com> 
Original-Maintainer: Diego Fernández Durán <diego@goedi.net>
Bugs: https://bugs.launchpad.net/ubuntu/+filebug 
Installed-Size: 48
Depends: libc6 (>= 2.4), libncurses5 (>= 6), libtinfo5 (>= 6) 
Recommends: kbd
Suggests: cmatrix-xfont
Filename: pool/universe/c/cmatrix/cmatrix_2.0-2_amd64.deb
Size: 16084
MD5sum: 8dad2a99d74b63cce6eeff0046f0ac91 
SHA1: 3da3a0ec97807e6f53de7653e4e9f47fd96521c2
SHA256: cd50212101bfd71479af41e7afc47ea822c075ddb1ceed83895f8eaa1b79ce5d Homepage: http://www.asty.org/cmatrix/
Description-en_CA: simulates the display from "The Matrix" 
Screen saver for the terminal based in the movie "The Matrix".
 * Support terminal resize.
 * Screen saver mode: any key closes it.
 * Selectable color.
 * Change text scroll rate.
Description-md5: 9af1f58e4b6301a6583f036c780c6ae6
```

You can see a lot of useful information in the output, including the
package description and the contact information of the maintainer of the
package, which is useful if you find a bug and want to report it. You
will also find out if the package depends on (requires) other packages.

**Package dependency** can turn into a nightmare, and so I highly
recommend that you use the [apt-get install] command to install a
package whenever possible as it checks and resolves package dependency
while installing a package. On the other hand, the [dpkg -i]
command doesn't check for package dependency. Keep that in mind!

You can use the [apt-cache depends] command to list package
dependencies:

``` 
apt-cache depends package_name
```

For example, to view the list of packages that are needed to be
installed for [cmatrix] to work properly, you can run the command:

``` 
root@ubuntu-linux:~# apt-cache depends cmatrix 
cmatrix
  Depends: libc6 
  Depends: libncurses6 
  Depends: libtinfo6 
  Recommends: kbd 
  Suggests: cmatrix-xfont
```

As you can see, the [cmatrix] package depends on three packages:

-   [libc6]
-   [libncurses6]
-   [libtinfo6]

Those three packages have to be installed on the system in order for
[cmatrix] to run properly.


Listing all packages
====================


You can use the [dpkg -l] command to list all the packages that
are installed on your system:

``` 
root@ubuntu-linux:~# dpkg -l
```

You can also use the [apt-cache pkgnames] command to list all the
packages that are available for you to install:

``` 
root@ubuntu-linux:~# apt-cache pkgnames 
libdatrie-doc
libfstrcmp0-dbg 
libghc-monadplus-doc 
librime-data-sampheng 
python-pyao-dbg 
fonts-georgewilliams
python3-aptdaemon.test 
libcollada2gltfconvert-dev 
python3-doc8
r-bioc-hypergraph
.
.
.
.
.
```

You can pipe the output to the [wc -l] command to get the total
number of available packages:

``` 
root@ubuntu-linux:~# apt-cache pkgnames | wc -l
```

Wow! That's a massive number; over 79,000 available packages on my
system.


You can use the [apt-cache policy] command to list all the
enabled repositories on your system:

``` 
root@ubuntu-linux:~# apt-cache policy 
Package files:
100 /var/lib/dpkg/status 
    release a=now
500 http://dl.google.com/linux/chrome/deb stable/main amd64 
    Packages release v=1.0,o=Google LLC,a=stable,n=stable,l=Google,c=main,
    b=amd64 origin dl.google.com
100 http://ca.archive.ubuntu.com/ubuntu bionic-backports/main i386 
    Packages release v=18.04,o=Ubuntu,a=bionic-backports,n=bionic,l=Ubuntu,
    c=main,b=i386 origin ca.archive.ubuntu.com
100 http://ca.archive.ubuntu.com/ubuntu bionic-backports/main amd64 
    Packages release v=18.04,o=Ubuntu,a=bionic-backports,n=bionic,l=Ubuntu,
    c=main,b=amd64 origin ca.archive.ubuntu.com
500 http://ca.archive.ubuntu.com/ubuntu bionic/multiverse i386 
    Packages release v=18.04,o=Ubuntu,a=bionic,n=bionic,
    l=Ubuntu,c=multiverse,b=i386 origin ca.archive.ubuntu.com
500 http://ca.archive.ubuntu.com/ubuntu bionic/multiverse amd64 
    Packages release v=18.04,o=Ubuntu,a=bionic,n=bionic,l=Ubuntu,
    c=multiverse,b=amd64 origin ca.archive.ubuntu.com
500 http://ca.archive.ubuntu.com/ubuntu bionic/universe i386 
    Packages release v=18.04,o=Ubuntu,a=bionic,n=bionic,l=Ubuntu,
    c=universe,b=i386 origin ca.archive.ubuntu.com
500 http://ca.archive.ubuntu.com/ubuntu bionic/universe amd64 
    Packages release v=18.04,o=Ubuntu,a=bionic,n=bionic,l=Ubuntu,
    c=universe,b=amd64 origin ca.archive.ubuntu.com
500 http://ca.archive.ubuntu.com/ubuntu bionic/restricted i386 
    Packages release v=18.04,o=Ubuntu,a=bionic,n=bionic,l=Ubuntu,
    c=restricted,b=i386 origin ca.archive.ubuntu.com
500 http://ca.archive.ubuntu.com/ubuntu bionic/restricted amd64 
    Packages release v=18.04,o=Ubuntu,a=bionic,n=bionic,l=Ubuntu,
    c=restricted,b=amd64 origin ca.archive.ubuntu.com
500 http://ca.archive.ubuntu.com/ubuntu bionic/main i386 
    Packages release v=18.04,o=Ubuntu,a=bionic,
    n=bionic,l=Ubuntu,c=main,b=i386 origin ca.archive.ubuntu.com
500 http://ca.archive.ubuntu.com/ubuntu bionic/main amd64 
    Packages release v=18.04,o=Ubuntu,a=bionic,n=bionic,
    l=Ubuntu,c=main,b=amd64 origin ca.archive.ubuntu.com
Pinned packages:
```

If you are eager to know which repository provides a specific package,
you can use the [apt-cache policy] command followed by the package
name:

``` 
apt-cache policy package_name
```

For example, to know which repository provides the [cmatrix]
package, you can run:

``` 
root@ubuntu-linux:~# apt-cache policy cmatrix 
cmatrix:
  Installed: 1.2a-5build3 
  Candidate: 1.2a-5build3 
  Version table:
*** 1.2a-5build3 500
    500 http://ca.archive.ubuntu.com/ubuntu bionic/universe amd64 Packages
    100 /var/lib/dpkg/status
```


Patching your system
====================


If a newer release for a package is available, then you can upgrade it
using the [apt-get install \--only-upgrade] command followed by
the package name:

``` 
apt-get install --only-upgrade package_name
```

For example, you can upgrade the [nano] package by running the
command:

``` 
root@ubuntu-linux:~# apt-get install --only-upgrade nano 
Reading package lists... Done
Building dependency tree
Reading state information... Done
nano is already the newest version (2.9.3-2).
The following package was automatically installed and is no longer required: 
  hoichess
Use 'apt autoremove' to remove it.
0 upgraded, 0 newly installed, 0 to remove and 357 not upgraded.
```

You can also upgrade all the installed packages on your system by
running the commands:

1.  [apt-get update]
2.  [apt-get upgrade]

The first command [apt-get update] will update the list of
available packages and their versions, but it doesn't do any
installation or upgrade:

``` 
root@ubuntu-linux:~# apt-get update
Ign:1 http://dl.google.com/linux/chrome/deb stable InRelease 
Hit:2 http://ca.archive.ubuntu.com/ubuntu bionic InRelease
Hit:3 http://ppa.launchpad.net/linuxuprising/java/ubuntu bionic InRelease 
Hit:4 http://dl.google.com/linux/chrome/deb stable Release
Hit:5 http://security.ubuntu.com/ubuntu bionic-security InRelease 
Hit:6 http://ca.archive.ubuntu.com/ubuntu bionic-updates InRelease 
Hit:8 http://ca.archive.ubuntu.com/ubuntu bionic-backports InRelease 
Reading package lists... Done
```

The second command [apt-get upgrade] will upgrade all the
installed packages on your system:

``` 
root@ubuntu-linux:~# apt-get upgrade 
Reading package lists... Done 
Building dependency tree
Reading state information... Done 
Calculating upgrade... Done
The following package was automatically installed and is no longer required: 
  hoichess
Use 'apt autoremove' to remove it.
The following packages have been kept back:
  gstreamer1.0-gl libcogl20 libgail-3-0 libgl1-mesa-dri libgstreamer-gl1.0-0 
  libreoffice-calc libreoffice-core libreoffice-draw libreoffice-gnome 
    libreoffice-gtk3 
  libwayland-egl1-mesa libxatracker2 linux-generic linux-headers-generic
  software-properties-common software-properties-gtk ubuntu-desktop 
The following packages will be upgraded:
  apt apt-utils aptdaemon aptdaemon-data aspell base-files bash bind9-host bluez 
  python2.7-minimal python3-apt python3-aptdaemon python3-aptdaemon.gtk3widgets 
  python3-problem-report python3-update-manager python3-urllib3 python3.6
342 upgraded, 0 newly installed, 0 to remove and 30 not upgraded. 
Need to get 460 MB of archives.
After this operation, 74.3 MB of additional disk space will be used. 
Do you want to continue? [Y/n]
```

Remember that order matters; that is, you need to run the [apt-get
update] command before you run the [apt-get upgrade]
command.

In Linux lingo, the process of upgrading all the installed packages on
your system is called **patching the system**.


Knowledge check
===============


For the following exercises, open up your Terminal and try to solve the
following tasks:

1.  Install the [tmux] package on your system.
2.  List all the dependencies of the [vim] package.
3.  Install the [cowsay] package on your system.
4.  Remove the [cowsay] package along with all its configuration
    files.
5.  Upgrade all the packages on your system (patch your system).
