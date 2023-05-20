Symptomes:
after `sudo apt upgrade`
```
Preparing to unpack .../224-libc-ares2_1.18.1-1ubuntu0.22.04.1_amd64.deb ...
Unpacking libc-ares2:amd64 (1.18.1-1ubuntu0.22.04.1) over (1.18.1-1build1) ...
Selecting previously unselected package proj-bin.
Preparing to unpack .../225-proj-bin_8.2.1-1_amd64.deb ...
Unpacking proj-bin (8.2.1-1) ...
Errors were encountered while processing:
 /tmp/apt-dpkg-install-vlN1i6/097-libmlt-data_7.16.0-1~ubuntu22.04.1_all.deb
 /tmp/apt-dpkg-install-vlN1i6/098-melt_7.16.0-1~ubuntu22.04.1_amd64.deb
E: Sub-process /usr/bin/dpkg returned an error code (1)
```
And `sudo apt --fix-broken install` fails as follows:

```
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
Correcting dependencies... Done
The following packages were automatically installed and are no longer required:
  docker-scan-plugin libmlt7-data linux-headers-6.0.12-76060006
  linux-headers-6.0.12-76060006-generic linux-image-6.0.12-76060006-generic
  linux-modules-6.0.12-76060006-generic linux-tools-6.0.12-76060006
  linux-tools-6.0.12-76060006-generic melt-7
Use 'sudo apt autoremove' to remove them.
The following additional packages will be installed:
  libmlt-data melt
The following NEW packages will be installed:
  libmlt-data melt
0 upgraded, 2 newly installed, 0 to remove and 13 not upgraded.
267 not fully installed or removed.
Need to get 0 B/128 kB of archives.
After this operation, 826 kB of additional disk space will be used.
Do you want to continue? [Y/n] y
(Reading database ... 382914 files and directories currently installed.)
Preparing to unpack .../libmlt-data_7.16.0-1~ubuntu22.04.1_all.deb ...
Unpacking libmlt-data (7.16.0-1~ubuntu22.04.1) ...
dpkg: error processing archive /var/cache/apt/archives/libmlt-data_7.16.0-1~ubuntu22.04.1_all.deb (--u
npack):
 trying to overwrite '/usr/share/mlt-7/avformat/blacklist.txt', which is also in package libmlt7-data 
7.14.0-1~ubuntu22.04.1
Preparing to unpack .../melt_7.16.0-1~ubuntu22.04.1_amd64.deb ...
Unpacking melt (7.16.0-1~ubuntu22.04.1) ...
dpkg: error processing archive /var/cache/apt/archives/melt_7.16.0-1~ubuntu22.04.1_amd64.deb (--unpack
):
 trying to overwrite '/usr/bin/melt-7', which is also in package melt-7 7.14.0-1~ubuntu22.04.1
Errors were encountered while processing:
 /var/cache/apt/archives/libmlt-data_7.16.0-1~ubuntu22.04.1_all.deb
 /var/cache/apt/archives/melt_7.16.0-1~ubuntu22.04.1_amd64.deb
E: Sub-process /usr/bin/dpkg returned an error code (1)

```

Then, as suggested by this stackoverflow question (not the dangerous reply!), you may use `sudo dpkg -P` to remove a package.
The idea is to remove all packages that makes conflicts as follows (specific to the case).

```
sudo dpkg -P libmlt7-data
sudo dpkg -P melt-7
```

Then by running `sudo apt --fix-broken install`, the process of upgrade finished without any error.


