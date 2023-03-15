
Knowledge check 1
=================


1.  [cal 2023]
2.  [free -h]
3.  [ls /home/elliot]
4.  [passwd]
5.  echo \"Mr.Robot is an awesome TV show!\"

True or false
-------------

1.  False
2.  False
3.  True
4.  False
5.  True


Knowledge check 2
=================


1.  [ls -l /var/log]
2.  [cat /etc/hostname]
3.  [touch file1 file2 file3]
4.  [ls -a /home/elliot]
5.  [mkdir /home/elliot/fsociety]

True or false
-------------

1.  False
2.  False
3.  True
4.  False
5.  True


Knowledge check 3
=================


1.  [head -n 2 facts.txt]
2.  [tail -n 1 facts.txt]
3.  [tac facts.txt]
4.  [vi facts.txt]
5.  [:q]


Knowledge check 4
=================


1.  [touch hacker1 hacker2 hacker3]
2.  [mkdir Linux Windows Mac]
3.  [touch Linux/cool]
4.  [touch Windows/boring]
5.  [touch Mac/expensive]
6.  [cp hacker1 hacker2 /tmp]
7.  [cp -r Windows Mac/tmp]
8.  [mv hacker3 /tmp]
9.  [mv Linux /tmp]
10. [rm Mac/expensive]
11. [rmdir Mac]
12. [rm -r Windows]
13. [rm hacker2]
14. [mv hacker1 hacker01]

True or false
-------------

1.  False
2.  False
3.  True
4.  False
5.  True


Knowledge check 5
=================


1.  [type echo]
2.  [which uptime]
3.  [whatis mkdir]
4.  [man mv]
5.  [apropos calendar]
6.  [help history]

True or false
-------------

1.  False
2.  False
3.  True
4.  True


Knowledge check 6
=================


1.  [ls -id /var/log]
2.  [stat /boot]
3.  [mkdir coins]
4.  [ln -s coins currency]
5.  [touch coins/silver coins/gold]
6.  [touch currency/bronze]
7.  [ls coins currency]
8.  [ln beverages drinks]
9.  [rm beverages]
10. [cat drinks]

True or false
-------------

1.  False
2.  True
3.  True
4.  False
5.  True
6.  False
7.  True


Knowledge check 7
=================


1.  [su root]
2.  [passwd root]
3.  [su - elliot]
4.  [su]

True or false
-------------

1.  True
2.  True
3.  False


Knowledge check 8
=================


1.  [useradd -u 333 abraham]
2.  [groupadd admins]
3.  [usermod -aG admins abraham]
4.  [chgrp admins /home/abraham]
5.  [chmod g=r /home/abraham]

True or false
-------------

1.  True
2.  False
3.  False


Knowledge check 9
=================


1.  [head -n 5 facts.txt *\|* tail -n 1]
2.  [free \> system.txt]
3.  [lscpu \>\> system.txt]
4.  [rmdir /var 2\> error.txt]


Knowledge check 10
==================


1.  [du -b /etc/hostname]
2.  [cut -d: -f1 /etc/group]
3.  [wc -l /etc/services]
4.  [grep bash /etc/passwd]
5.  [uptime *\|* tr \[:lower:\] \[:upper:\]]


Knowledge check 11
==================


1.  [locate boot.log]
2.  [find / -size +50M]
3.  [find / -size +70M -size -100M]
4.  [find / -user smurf]
5.  [find / -group developers]


Knowledge check 12
==================


1.  [apt-get install tmux]
2.  [apt-cache depends vim]
3.  [apt-get install cowsay]
4.  [apt-get purge cowsay]
5.  [apt-get update then run apt-get upgrade]


Knowledge check 13
==================


1.  [pgrep terminal]
2.  [ps -fp pid\_of\_terminal]
3.  [kill -9 pid\_of\_terminal]
4.  [firefox &]
5.  [renice -n -20 pid\_of\_firefox]


Knowledge check 14
==================


1.  [smurf ALL=(ALL) /sbin/fdisk]
2.  [%developers ALL=(ALL) /usr/bin/apt-get]
3.  [sudo -lU smurf]


Knowledge check 15
==================


1.  [hostnamectl set-hostname darkarmy]
2.  [netstat -rn or ip route]
3.  [traceroute www.ubuntu.com]
4.  [cat /etc/resolv.conf]
5.  [nslookup www.distrowatch.com]
6.  [ifconfig eth0 down]
7.  [ifconfig eth0 up]


Knowledge check 16
==================


1.  
    ```
    #!/bin/bash
     cal
    ```

2.  
    ```
    #!/bin/bash
     cal $1
    ```
3.  
    ```
    #!/bin/bash
     for i in {2000..2020}; do
            cal $i
     done
    ```
    


Knowledge check 17
==================


1.  [\*/10 \* \* \* \* echo \"10 minutes have passed!\" \>\>
    /root/minutes.txt]
2.  [0 1 25 12 \* echo \"Merry Christmas!\" \>\>
    /root/holidays.txt]


Knowledge check 18
==================


1.  [tar -cvf /root/var.tar.gz /var]
2.  [tar -jvf /root/tmp.tar.bz2 /tmp]
3.  [tar -Jvf /root/etc.tar.xz /etc]


Knowledge check 19
==================


1.  [alias ins="apt-get install"]

2.  [alias packages="dpkg -l"]

3.  Add the line\
    [alias clean=\"rm -r /tmp/\*\"]\

    to the end of the [.bashrc] file.

