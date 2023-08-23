### Changes to be made in `/root/airflow/airflow.cfg` file
```cfg
[core]
dags_folder = /opt/airflow/dags
default_timezone = utc
executor = CeleryExecutor
load_examples = False
[database]
sql_alchemy_conn = postgres://postgres:postgres@172.17.0.3:5432/postgres
[celery]
broker_url = pyamqp://guest:guest@172.17.0.4:5672/
```

Last login: Thu Aug 24 00:12:33 on ttys010
env /usr/bin/arch -x86_64 /bin/zsh --login
ambujsingh@HAT-IN-LAP-080 ~ % env /usr/bin/arch -x86_64 /bin/zsh --login
ambujsingh@HAT-IN-LAP-080 ~ % docker run -it --name airflow_v1 -p -v /Users/ambujsingh/Documents/Airflow/dags:/opt/airflow/dags -e TZ=UTC ubuntu:latest /bin/bash 
docker: Invalid containerPort: -v.
See 'docker run --help'.
ambujsingh@HAT-IN-LAP-080 ~ % docker run -it --name airflow_v1 -v /Users/ambujsingh/Documents/Airflow/dags:/opt/airflow/dags -e TZ=UTC ubuntu:latest /bin/bash 
root@2a2814f91f18:/# apt-get update
Get:1 http://ports.ubuntu.com/ubuntu-ports jammy InRelease [270 kB]
Get:2 http://ports.ubuntu.com/ubuntu-ports jammy-updates InRelease [119 kB]                                                                                                                                
Get:3 http://ports.ubuntu.com/ubuntu-ports jammy-backports InRelease [109 kB]                                                                                                                              
Get:4 http://ports.ubuntu.com/ubuntu-ports jammy-security InRelease [110 kB]                                                                                                                               
Get:5 http://ports.ubuntu.com/ubuntu-ports jammy/restricted arm64 Packages [24.2 kB]                                                                                                                       
Get:6 http://ports.ubuntu.com/ubuntu-ports jammy/universe arm64 Packages [17.2 MB]                                                                                                                         
Get:7 http://ports.ubuntu.com/ubuntu-ports jammy/multiverse arm64 Packages [224 kB]                                                                                                                        
Get:8 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 Packages [1758 kB]                                                                                                                             
Get:9 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 Packages [1016 kB]                                                                                                                     
Get:10 http://ports.ubuntu.com/ubuntu-ports jammy-updates/multiverse arm64 Packages [27.8 kB]                                                                                                              
Get:11 http://ports.ubuntu.com/ubuntu-ports jammy-updates/universe arm64 Packages [1123 kB]                                                                                                                
Get:12 http://ports.ubuntu.com/ubuntu-ports jammy-updates/restricted arm64 Packages [556 kB]                                                                                                               
Get:13 http://ports.ubuntu.com/ubuntu-ports jammy-backports/main arm64 Packages [48.8 kB]                                                                                                                  
Get:14 http://ports.ubuntu.com/ubuntu-ports jammy-backports/universe arm64 Packages [23.7 kB]                                                                                                              
Get:15 http://ports.ubuntu.com/ubuntu-ports jammy-security/restricted arm64 Packages [548 kB]                                                                                                              
Get:16 http://ports.ubuntu.com/ubuntu-ports jammy-security/main arm64 Packages [748 kB]                                                                                                                    
Get:17 http://ports.ubuntu.com/ubuntu-ports jammy-security/universe arm64 Packages [869 kB]                                                                                                                
Get:18 http://ports.ubuntu.com/ubuntu-ports jammy-security/multiverse arm64 Packages [23.4 kB]                                                                                                             
Fetched 24.8 MB in 1min 42s (243 kB/s)                                                                                                                                                                     
Reading package lists... Done
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# apt-get install -y python3-pip
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
  binutils binutils-aarch64-linux-gnu binutils-common build-essential bzip2 ca-certificates cpp cpp-11 dirmngr dpkg-dev fakeroot fontconfig-config fonts-dejavu-core g++ g++-11 gcc gcc-11 gcc-11-base
  gnupg gnupg-l10n gnupg-utils gpg gpg-agent gpg-wks-client gpg-wks-server gpgconf gpgsm javascript-common libalgorithm-diff-perl libalgorithm-diff-xs-perl libalgorithm-merge-perl libasan6 libassuan0
  libatomic1 libbinutils libbrotli1 libbsd0 libc-dev-bin libc-devtools libc6-dev libcc1-0 libcrypt-dev libctf-nobfd0 libctf0 libdeflate0 libdpkg-perl libexpat1 libexpat1-dev libfakeroot
  libfile-fcntllock-perl libfontconfig1 libfreetype6 libgcc-11-dev libgd3 libgdbm-compat4 libgdbm6 libgomp1 libhwasan0 libisl23 libitm1 libjbig0 libjpeg-turbo8 libjpeg8 libjs-jquery libjs-sphinxdoc
  libjs-underscore libksba8 libldap-2.5-0 libldap-common liblocale-gettext-perl liblsan0 libmd0 libmpc3 libmpdec3 libmpfr6 libnpth0 libnsl-dev libperl5.34 libpng16-16 libpython3-dev libpython3-stdlib
  libpython3.10 libpython3.10-dev libpython3.10-minimal libpython3.10-stdlib libreadline8 libsasl2-2 libsasl2-modules libsasl2-modules-db libsqlite3-0 libstdc++-11-dev libtiff5 libtirpc-dev libtsan0
  libubsan1 libwebp7 libx11-6 libx11-data libxau6 libxcb1 libxdmcp6 libxpm4 linux-libc-dev lto-disabled-list make manpages manpages-dev media-types netbase openssl patch perl perl-modules-5.34
  pinentry-curses python3 python3-dev python3-distutils python3-lib2to3 python3-minimal python3-pkg-resources python3-setuptools python3-wheel python3.10 python3.10-dev python3.10-minimal
  readline-common rpcsvc-proto ucf xz-utils zlib1g-dev
Suggested packages:
  binutils-doc bzip2-doc cpp-doc gcc-11-locales dbus-user-session libpam-systemd pinentry-gnome3 tor debian-keyring gcc-11-doc gcc-multilib autoconf automake libtool flex bison gdb gcc-doc parcimonie
  xloadimage scdaemon apache2 | lighttpd | httpd glibc-doc git bzr libgd-tools gdbm-l10n libsasl2-modules-gssapi-mit | libsasl2-modules-gssapi-heimdal libsasl2-modules-ldap libsasl2-modules-otp
  libsasl2-modules-sql libstdc++-11-doc make-doc man-browser ed diffutils-doc perl-doc libterm-readline-gnu-perl | libterm-readline-perl-perl libtap-harness-archive-perl pinentry-doc python3-doc
  python3-tk python3-venv python-setuptools-doc python3.10-venv python3.10-doc binfmt-support readline-doc
The following NEW packages will be installed:
  binutils binutils-aarch64-linux-gnu binutils-common build-essential bzip2 ca-certificates cpp cpp-11 dirmngr dpkg-dev fakeroot fontconfig-config fonts-dejavu-core g++ g++-11 gcc gcc-11 gcc-11-base
  gnupg gnupg-l10n gnupg-utils gpg gpg-agent gpg-wks-client gpg-wks-server gpgconf gpgsm javascript-common libalgorithm-diff-perl libalgorithm-diff-xs-perl libalgorithm-merge-perl libasan6 libassuan0
  libatomic1 libbinutils libbrotli1 libbsd0 libc-dev-bin libc-devtools libc6-dev libcc1-0 libcrypt-dev libctf-nobfd0 libctf0 libdeflate0 libdpkg-perl libexpat1 libexpat1-dev libfakeroot
  libfile-fcntllock-perl libfontconfig1 libfreetype6 libgcc-11-dev libgd3 libgdbm-compat4 libgdbm6 libgomp1 libhwasan0 libisl23 libitm1 libjbig0 libjpeg-turbo8 libjpeg8 libjs-jquery libjs-sphinxdoc
  libjs-underscore libksba8 libldap-2.5-0 libldap-common liblocale-gettext-perl liblsan0 libmd0 libmpc3 libmpdec3 libmpfr6 libnpth0 libnsl-dev libperl5.34 libpng16-16 libpython3-dev libpython3-stdlib
  libpython3.10 libpython3.10-dev libpython3.10-minimal libpython3.10-stdlib libreadline8 libsasl2-2 libsasl2-modules libsasl2-modules-db libsqlite3-0 libstdc++-11-dev libtiff5 libtirpc-dev libtsan0
  libubsan1 libwebp7 libx11-6 libx11-data libxau6 libxcb1 libxdmcp6 libxpm4 linux-libc-dev lto-disabled-list make manpages manpages-dev media-types netbase openssl patch perl perl-modules-5.34
  pinentry-curses python3 python3-dev python3-distutils python3-lib2to3 python3-minimal python3-pip python3-pkg-resources python3-setuptools python3-wheel python3.10 python3.10-dev python3.10-minimal
  readline-common rpcsvc-proto ucf xz-utils zlib1g-dev
0 upgraded, 131 newly installed, 0 to remove and 2 not upgraded.
Need to get 98.0 MB of archives.
After this operation, 341 MB of additional disk space will be used.
Get:1 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 liblocale-gettext-perl arm64 1.07-4build3 [16.9 kB]
Get:2 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libpython3.10-minimal arm64 3.10.12-1~22.04.2 [809 kB]
Get:3 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libexpat1 arm64 2.4.7-1ubuntu0.2 [76.8 kB]                                                                                             
Get:4 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 python3.10-minimal arm64 3.10.12-1~22.04.2 [2247 kB]                                                                                   
Get:5 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 python3-minimal arm64 3.10.6-1~22.04 [24.3 kB]                                                                                         
Get:6 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 media-types all 7.0.0 [25.5 kB]                                                                                                                
Get:7 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libmpdec3 arm64 2.5.1-2build2 [89.0 kB]                                                                                                        
Get:8 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 readline-common all 8.1.2-1 [53.5 kB]                                                                                                          
Get:9 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libreadline8 arm64 8.1.2-1 [153 kB]                                                                                                            
Get:10 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libsqlite3-0 arm64 3.37.2-2ubuntu0.1 [636 kB]                                                                                         
Get:11 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libpython3.10-stdlib arm64 3.10.12-1~22.04.2 [1845 kB]                                                                                
Get:12 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 python3.10 arm64 3.10.12-1~22.04.2 [509 kB]                                                                                           
Get:13 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libpython3-stdlib arm64 3.10.6-1~22.04 [6910 B]                                                                                       
Get:14 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 python3 arm64 3.10.6-1~22.04 [22.8 kB]                                                                                                
Get:15 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 perl-modules-5.34 all 5.34.0-3ubuntu1.2 [2977 kB]                                                                                     
Get:16 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libgdbm6 arm64 1.23-1 [34.1 kB]                                                                                                               
Get:17 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libgdbm-compat4 arm64 1.23-1 [6294 B]                                                                                                         
Get:18 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libperl5.34 arm64 5.34.0-3ubuntu1.2 [4726 kB]                                                                                         
Get:19 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 perl arm64 5.34.0-3ubuntu1.2 [232 kB]                                                                                                 
Get:20 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 openssl arm64 3.0.2-0ubuntu1.10 [1164 kB]                                                                                             
Get:21 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 ca-certificates all 20230311ubuntu0.22.04.1 [155 kB]                                                                                  
Get:22 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libmd0 arm64 1.0.4-1build1 [23.8 kB]                                                                                                          
Get:23 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libbsd0 arm64 0.11.5-1 [43.7 kB]                                                                                                              
Get:24 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 netbase all 6.3 [12.9 kB]                                                                                                                     
Get:25 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 python3-pkg-resources all 59.6.0-1.2ubuntu0.22.04.1 [132 kB]                                                                          
Get:26 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 ucf all 3.0043 [56.1 kB]                                                                                                                      
Get:27 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libpng16-16 arm64 1.6.37-3build5 [189 kB]                                                                                                     
Get:28 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libxau6 arm64 1:1.0.9-1build5 [7624 B]                                                                                                        
Get:29 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libxdmcp6 arm64 1:1.1.3-0ubuntu5 [10.8 kB]                                                                                                    
Get:30 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libxcb1 arm64 1.14-3ubuntu3 [49.0 kB]                                                                                                         
Get:31 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libx11-data all 2:1.7.5-1ubuntu0.2 [119 kB]                                                                                           
Get:32 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libx11-6 arm64 2:1.7.5-1ubuntu0.2 [661 kB]                                                                                            
Get:33 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 manpages all 5.10-1ubuntu1 [1375 kB]                                                                                                          
Get:34 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 xz-utils arm64 5.2.5-2ubuntu1 [84.4 kB]                                                                                                       
Get:35 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 binutils-common arm64 2.38-4ubuntu2.3 [222 kB]
Get:36 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libbinutils arm64 2.38-4ubuntu2.3 [825 kB]                                                                                            
Get:37 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libctf-nobfd0 arm64 2.38-4ubuntu2.3 [108 kB]                                                                                          
Get:38 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libctf0 arm64 2.38-4ubuntu2.3 [103 kB]                                                                                                
Get:39 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 binutils-aarch64-linux-gnu arm64 2.38-4ubuntu2.3 [3230 kB]                                                                            
Get:40 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 binutils arm64 2.38-4ubuntu2.3 [3162 B]                                                                                               
Get:41 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libc-dev-bin arm64 2.35-0ubuntu3.1 [19.6 kB]
Get:42 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 linux-libc-dev arm64 5.15.0-79.86 [1314 kB]
Get:43 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libcrypt-dev arm64 1:4.4.27-1 [119 kB]                                                                                                        
Get:44 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 rpcsvc-proto arm64 1.4.2-0ubuntu6 [65.4 kB]                                                                                                   
Get:45 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libtirpc-dev arm64 1.3.2-2ubuntu0.1 [199 kB]                                                                                          
Get:46 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libnsl-dev arm64 1.3.0-2build2 [72.1 kB]                                                                                                      
Get:47 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libc6-dev arm64 2.35-0ubuntu3.1 [1544 kB]                                                                                             
Get:48 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 gcc-11-base arm64 11.4.0-1ubuntu1~22.04 [20.3 kB]                                                                                     
Get:49 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libisl23 arm64 0.24-2build1 [689 kB]                                                                                                          
Get:50 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libmpfr6 arm64 4.1.0-3build3 [245 kB]                                                                                                         
Get:51 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libmpc3 arm64 1.2.1-2build1 [48.1 kB]                                                                                                         
Get:52 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 cpp-11 arm64 11.4.0-1ubuntu1~22.04 [9762 kB]                                                                                          
Get:53 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 cpp arm64 4:11.2.0-1ubuntu1 [27.7 kB]                                                                                                         
Get:54 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libcc1-0 arm64 12.3.0-1ubuntu1~22.04 [45.0 kB]                                                                                        
Get:55 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libgomp1 arm64 12.3.0-1ubuntu1~22.04 [124 kB]                                                                                         
Get:56 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libitm1 arm64 12.3.0-1ubuntu1~22.04 [28.4 kB]                                                                                         
Get:57 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libatomic1 arm64 12.3.0-1ubuntu1~22.04 [10.8 kB]                                                                                      
Get:58 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libasan6 arm64 11.4.0-1ubuntu1~22.04 [2234 kB]                                                                                        
Get:59 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 liblsan0 arm64 12.3.0-1ubuntu1~22.04 [1035 kB]                                                                                        
Get:60 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libtsan0 arm64 11.4.0-1ubuntu1~22.04 [2235 kB]                                                                                        
Get:61 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libubsan1 arm64 12.3.0-1ubuntu1~22.04 [965 kB]                                                                                        
Get:62 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libhwasan0 arm64 12.3.0-1ubuntu1~22.04 [1117 kB]                                                                                      
Get:63 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libgcc-11-dev arm64 11.4.0-1ubuntu1~22.04 [1146 kB]                                                                                   
Get:64 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 gcc-11 arm64 11.4.0-1ubuntu1~22.04 [19.4 MB]                                                                                          
Get:65 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 gcc arm64 4:11.2.0-1ubuntu1 [5128 B]                                                                                                          
Get:66 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libstdc++-11-dev arm64 11.4.0-1ubuntu1~22.04 [2088 kB]                                                                                
Get:67 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 g++-11 arm64 11.4.0-1ubuntu1~22.04 [11.1 MB]                                                                                          
Get:68 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 g++ arm64 4:11.2.0-1ubuntu1 [1394 B]                                                                                                          
Get:69 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 make arm64 4.3-4.1build1 [177 kB]                                                                                                             
Get:70 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libdpkg-perl all 1.21.1ubuntu2.2 [237 kB]                                                                                             
Get:71 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 bzip2 arm64 1.0.8-5build1 [34.6 kB]                                                                                                           
Get:72 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 patch arm64 2.7.6-7build2 [105 kB]                                                                                                            
Get:73 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 lto-disabled-list all 24 [12.5 kB]                                                                                                            
Get:74 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 dpkg-dev all 1.21.1ubuntu2.2 [922 kB]                                                                                                 
Get:75 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 build-essential arm64 12.9ubuntu3 [4740 B]                                                                                                    
Get:76 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libassuan0 arm64 2.5.5-1build1 [36.5 kB]                                                                                                      
Get:77 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 gpgconf arm64 2.2.27-3ubuntu2.1 [92.5 kB]                                                                                             
Get:78 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libksba8 arm64 1.6.0-2ubuntu0.2 [117 kB]                                                                                              
Get:79 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libsasl2-modules-db arm64 2.1.27+dfsg2-3ubuntu1.2 [21.1 kB]                                                                           
Get:80 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libsasl2-2 arm64 2.1.27+dfsg2-3ubuntu1.2 [55.6 kB]                                                                                    
Get:81 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libldap-2.5-0 arm64 2.5.16+dfsg-0ubuntu0.22.04.1 [181 kB]                                                                             
Get:82 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libnpth0 arm64 1.6-3build2 [8156 B]                                                                                                           
Get:83 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 dirmngr arm64 2.2.27-3ubuntu2.1 [289 kB]                                                                                              
Get:84 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libfakeroot arm64 1.28-1ubuntu1 [31.5 kB]                                                                                                     
Get:85 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 fakeroot arm64 1.28-1ubuntu1 [60.5 kB]                                                                                                        
Get:86 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 fonts-dejavu-core all 2.37-2build1 [1041 kB]                                                                                                  
Get:87 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 fontconfig-config all 2.13.1-4.2ubuntu5 [29.1 kB]                                                                                             
Get:88 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 gnupg-l10n all 2.2.27-3ubuntu2.1 [54.4 kB]                                                                                            
Get:89 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 gnupg-utils arm64 2.2.27-3ubuntu2.1 [304 kB]                                                                                          
Get:90 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 gpg arm64 2.2.27-3ubuntu2.1 [506 kB]                                                                                                  
Get:91 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 pinentry-curses arm64 1.1.1-1build2 [33.5 kB]                                                                                                 
Get:92 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 gpg-agent arm64 2.2.27-3ubuntu2.1 [204 kB]                                                                                            
Get:93 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 gpg-wks-client arm64 2.2.27-3ubuntu2.1 [61.4 kB]                                                                                      
Get:94 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 gpg-wks-server arm64 2.2.27-3ubuntu2.1 [56.8 kB]                                                                                      
Get:95 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 gpgsm arm64 2.2.27-3ubuntu2.1 [192 kB]                                                                                                
Get:96 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 gnupg all 2.2.27-3ubuntu2.1 [315 kB]                                                                                                  
Get:97 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 javascript-common all 11+nmu1 [5936 B]                                                                                                        
Get:98 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libalgorithm-diff-perl all 1.201-1 [41.8 kB]                                                                                                  
Get:99 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libalgorithm-diff-xs-perl arm64 0.04-6build3 [11.7 kB]                                                                                        
Get:100 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libalgorithm-merge-perl all 0.08-3 [12.0 kB]                                                                                                 
Get:101 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libbrotli1 arm64 1.0.9-2build6 [314 kB]                                                                                                      
Get:102 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libfreetype6 arm64 2.11.1+dfsg-1ubuntu0.2 [383 kB]                                                                                   
Get:103 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libfontconfig1 arm64 2.13.1-4.2ubuntu5 [135 kB]                                                                                              
Get:104 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libjpeg-turbo8 arm64 2.1.2-0ubuntu1 [129 kB]                                                                                                 
Get:105 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libjpeg8 arm64 8c-2ubuntu10 [2264 B]                                                                                                         
Get:106 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libdeflate0 arm64 1.10-2 [69.1 kB]                                                                                                           
Get:107 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libjbig0 arm64 2.1-3.1ubuntu0.22.04.1 [29.1 kB]                                                                                      
Get:108 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libwebp7 arm64 1.2.2-2ubuntu0.22.04.1 [193 kB]                                                                                       
Get:109 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libtiff5 arm64 4.3.0-6ubuntu0.5 [180 kB]                                                                                             
Get:110 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libxpm4 arm64 1:3.5.12-1ubuntu0.22.04.1 [35.3 kB]                                                                                    
Get:111 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libgd3 arm64 2.3.0-2ubuntu2 [126 kB]                                                                                                         
Get:112 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libc-devtools arm64 2.35-0ubuntu3.1 [27.6 kB]                                                                                        
Get:113 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libexpat1-dev arm64 2.4.7-1ubuntu0.2 [129 kB]                                                                                        
Get:114 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libfile-fcntllock-perl arm64 0.22-3build7 [33.7 kB]                                                                                          
Get:115 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libjs-jquery all 3.6.0+dfsg+~3.5.13-1 [321 kB]                                                                                               
Get:116 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libjs-underscore all 1.13.2~dfsg-2 [118 kB]                                                                                                  
Get:117 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libjs-sphinxdoc all 4.3.2-1 [139 kB]                                                                                                         
Get:118 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libldap-common all 2.5.16+dfsg-0ubuntu0.22.04.1 [15.8 kB]                                                                            
Get:119 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libpython3.10 arm64 3.10.12-1~22.04.2 [1886 kB]                                                                                      
Get:120 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 zlib1g-dev arm64 1:1.2.11.dfsg-2ubuntu9.2 [163 kB]                                                                                   
Get:121 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libpython3.10-dev arm64 3.10.12-1~22.04.2 [4661 kB]                                                                                  
Get:122 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libpython3-dev arm64 3.10.6-1~22.04 [7168 B]                                                                                         
Get:123 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libsasl2-modules arm64 2.1.27+dfsg2-3ubuntu1.2 [68.4 kB]                                                                             
Get:124 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 manpages-dev all 5.10-1ubuntu1 [2309 kB]                                                                                                     
Get:125 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 python3.10-dev arm64 3.10.12-1~22.04.2 [508 kB]                                                                                      
Get:126 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 python3-lib2to3 all 3.10.8-1~22.04 [77.6 kB]                                                                                         
Get:127 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 python3-distutils all 3.10.8-1~22.04 [139 kB]                                                                                        
Get:128 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 python3-dev arm64 3.10.6-1~22.04 [26.0 kB]                                                                                           
Get:129 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 python3-setuptools all 59.6.0-1.2ubuntu0.22.04.1 [339 kB]                                                                            
Get:130 http://ports.ubuntu.com/ubuntu-ports jammy-updates/universe arm64 python3-wheel all 0.37.1-2ubuntu0.22.04.1 [32.0 kB]                                                                              
Get:131 http://ports.ubuntu.com/ubuntu-ports jammy-updates/universe arm64 python3-pip all 22.0.2+dfsg-1ubuntu0.3 [1305 kB]                                                                                 
Fetched 98.0 MB in 10min 49s (151 kB/s)                                                                                                                                                                    
debconf: delaying package configuration, since apt-utils is not installed
Selecting previously unselected package liblocale-gettext-perl.
(Reading database ... 4389 files and directories currently installed.)
Preparing to unpack .../liblocale-gettext-perl_1.07-4build3_arm64.deb ...
Unpacking liblocale-gettext-perl (1.07-4build3) ...
Selecting previously unselected package libpython3.10-minimal:arm64.
Preparing to unpack .../libpython3.10-minimal_3.10.12-1~22.04.2_arm64.deb ...
Unpacking libpython3.10-minimal:arm64 (3.10.12-1~22.04.2) ...
Selecting previously unselected package libexpat1:arm64.
Preparing to unpack .../libexpat1_2.4.7-1ubuntu0.2_arm64.deb ...
Unpacking libexpat1:arm64 (2.4.7-1ubuntu0.2) ...
Selecting previously unselected package python3.10-minimal.
Preparing to unpack .../python3.10-minimal_3.10.12-1~22.04.2_arm64.deb ...
Unpacking python3.10-minimal (3.10.12-1~22.04.2) ...
Setting up libpython3.10-minimal:arm64 (3.10.12-1~22.04.2) ...
Setting up libexpat1:arm64 (2.4.7-1ubuntu0.2) ...
Setting up python3.10-minimal (3.10.12-1~22.04.2) ...
Selecting previously unselected package python3-minimal.
(Reading database ... 4707 files and directories currently installed.)
Preparing to unpack .../0-python3-minimal_3.10.6-1~22.04_arm64.deb ...
Unpacking python3-minimal (3.10.6-1~22.04) ...
Selecting previously unselected package media-types.
Preparing to unpack .../1-media-types_7.0.0_all.deb ...
Unpacking media-types (7.0.0) ...
Selecting previously unselected package libmpdec3:arm64.
Preparing to unpack .../2-libmpdec3_2.5.1-2build2_arm64.deb ...
Unpacking libmpdec3:arm64 (2.5.1-2build2) ...
Selecting previously unselected package readline-common.
Preparing to unpack .../3-readline-common_8.1.2-1_all.deb ...
Unpacking readline-common (8.1.2-1) ...
Selecting previously unselected package libreadline8:arm64.
Preparing to unpack .../4-libreadline8_8.1.2-1_arm64.deb ...
Unpacking libreadline8:arm64 (8.1.2-1) ...
Selecting previously unselected package libsqlite3-0:arm64.
Preparing to unpack .../5-libsqlite3-0_3.37.2-2ubuntu0.1_arm64.deb ...
Unpacking libsqlite3-0:arm64 (3.37.2-2ubuntu0.1) ...
Selecting previously unselected package libpython3.10-stdlib:arm64.
Preparing to unpack .../6-libpython3.10-stdlib_3.10.12-1~22.04.2_arm64.deb ...
Unpacking libpython3.10-stdlib:arm64 (3.10.12-1~22.04.2) ...
Selecting previously unselected package python3.10.
Preparing to unpack .../7-python3.10_3.10.12-1~22.04.2_arm64.deb ...
Unpacking python3.10 (3.10.12-1~22.04.2) ...
Selecting previously unselected package libpython3-stdlib:arm64.
Preparing to unpack .../8-libpython3-stdlib_3.10.6-1~22.04_arm64.deb ...
Unpacking libpython3-stdlib:arm64 (3.10.6-1~22.04) ...
Setting up python3-minimal (3.10.6-1~22.04) ...
Selecting previously unselected package python3.
(Reading database ... 5137 files and directories currently installed.)
Preparing to unpack .../000-python3_3.10.6-1~22.04_arm64.deb ...
Unpacking python3 (3.10.6-1~22.04) ...
Selecting previously unselected package perl-modules-5.34.
Preparing to unpack .../001-perl-modules-5.34_5.34.0-3ubuntu1.2_all.deb ...
Unpacking perl-modules-5.34 (5.34.0-3ubuntu1.2) ...
Selecting previously unselected package libgdbm6:arm64.
Preparing to unpack .../002-libgdbm6_1.23-1_arm64.deb ...
Unpacking libgdbm6:arm64 (1.23-1) ...
Selecting previously unselected package libgdbm-compat4:arm64.
Preparing to unpack .../003-libgdbm-compat4_1.23-1_arm64.deb ...
Unpacking libgdbm-compat4:arm64 (1.23-1) ...
Selecting previously unselected package libperl5.34:arm64.
Preparing to unpack .../004-libperl5.34_5.34.0-3ubuntu1.2_arm64.deb ...
Unpacking libperl5.34:arm64 (5.34.0-3ubuntu1.2) ...
Selecting previously unselected package perl.
Preparing to unpack .../005-perl_5.34.0-3ubuntu1.2_arm64.deb ...
Unpacking perl (5.34.0-3ubuntu1.2) ...
Selecting previously unselected package openssl.
Preparing to unpack .../006-openssl_3.0.2-0ubuntu1.10_arm64.deb ...
Unpacking openssl (3.0.2-0ubuntu1.10) ...
Selecting previously unselected package ca-certificates.
Preparing to unpack .../007-ca-certificates_20230311ubuntu0.22.04.1_all.deb ...
Unpacking ca-certificates (20230311ubuntu0.22.04.1) ...
Selecting previously unselected package libmd0:arm64.
Preparing to unpack .../008-libmd0_1.0.4-1build1_arm64.deb ...
Unpacking libmd0:arm64 (1.0.4-1build1) ...
Selecting previously unselected package libbsd0:arm64.
Preparing to unpack .../009-libbsd0_0.11.5-1_arm64.deb ...
Unpacking libbsd0:arm64 (0.11.5-1) ...
Selecting previously unselected package netbase.
Preparing to unpack .../010-netbase_6.3_all.deb ...
Unpacking netbase (6.3) ...
Selecting previously unselected package python3-pkg-resources.
Preparing to unpack .../011-python3-pkg-resources_59.6.0-1.2ubuntu0.22.04.1_all.deb ...
Unpacking python3-pkg-resources (59.6.0-1.2ubuntu0.22.04.1) ...
Selecting previously unselected package ucf.
Preparing to unpack .../012-ucf_3.0043_all.deb ...
Moving old data out of the way
Unpacking ucf (3.0043) ...
Selecting previously unselected package libpng16-16:arm64.
Preparing to unpack .../013-libpng16-16_1.6.37-3build5_arm64.deb ...
Unpacking libpng16-16:arm64 (1.6.37-3build5) ...
Selecting previously unselected package libxau6:arm64.
Preparing to unpack .../014-libxau6_1%3a1.0.9-1build5_arm64.deb ...
Unpacking libxau6:arm64 (1:1.0.9-1build5) ...
Selecting previously unselected package libxdmcp6:arm64.
Preparing to unpack .../015-libxdmcp6_1%3a1.1.3-0ubuntu5_arm64.deb ...
Unpacking libxdmcp6:arm64 (1:1.1.3-0ubuntu5) ...
Selecting previously unselected package libxcb1:arm64.
Preparing to unpack .../016-libxcb1_1.14-3ubuntu3_arm64.deb ...
Unpacking libxcb1:arm64 (1.14-3ubuntu3) ...
Selecting previously unselected package libx11-data.
Preparing to unpack .../017-libx11-data_2%3a1.7.5-1ubuntu0.2_all.deb ...
Unpacking libx11-data (2:1.7.5-1ubuntu0.2) ...
Selecting previously unselected package libx11-6:arm64.
Preparing to unpack .../018-libx11-6_2%3a1.7.5-1ubuntu0.2_arm64.deb ...
Unpacking libx11-6:arm64 (2:1.7.5-1ubuntu0.2) ...
Selecting previously unselected package manpages.
Preparing to unpack .../019-manpages_5.10-1ubuntu1_all.deb ...
Unpacking manpages (5.10-1ubuntu1) ...
Selecting previously unselected package xz-utils.
Preparing to unpack .../020-xz-utils_5.2.5-2ubuntu1_arm64.deb ...
Unpacking xz-utils (5.2.5-2ubuntu1) ...
Selecting previously unselected package binutils-common:arm64.
Preparing to unpack .../021-binutils-common_2.38-4ubuntu2.3_arm64.deb ...
Unpacking binutils-common:arm64 (2.38-4ubuntu2.3) ...
Selecting previously unselected package libbinutils:arm64.
Preparing to unpack .../022-libbinutils_2.38-4ubuntu2.3_arm64.deb ...
Unpacking libbinutils:arm64 (2.38-4ubuntu2.3) ...
Selecting previously unselected package libctf-nobfd0:arm64.
Preparing to unpack .../023-libctf-nobfd0_2.38-4ubuntu2.3_arm64.deb ...
Unpacking libctf-nobfd0:arm64 (2.38-4ubuntu2.3) ...
Selecting previously unselected package libctf0:arm64.
Preparing to unpack .../024-libctf0_2.38-4ubuntu2.3_arm64.deb ...
Unpacking libctf0:arm64 (2.38-4ubuntu2.3) ...
Selecting previously unselected package binutils-aarch64-linux-gnu.
Preparing to unpack .../025-binutils-aarch64-linux-gnu_2.38-4ubuntu2.3_arm64.deb ...
Unpacking binutils-aarch64-linux-gnu (2.38-4ubuntu2.3) ...
Selecting previously unselected package binutils.
Preparing to unpack .../026-binutils_2.38-4ubuntu2.3_arm64.deb ...
Unpacking binutils (2.38-4ubuntu2.3) ...
Selecting previously unselected package libc-dev-bin.
Preparing to unpack .../027-libc-dev-bin_2.35-0ubuntu3.1_arm64.deb ...
Unpacking libc-dev-bin (2.35-0ubuntu3.1) ...
Selecting previously unselected package linux-libc-dev:arm64.
Preparing to unpack .../028-linux-libc-dev_5.15.0-79.86_arm64.deb ...
Unpacking linux-libc-dev:arm64 (5.15.0-79.86) ...
Selecting previously unselected package libcrypt-dev:arm64.
Preparing to unpack .../029-libcrypt-dev_1%3a4.4.27-1_arm64.deb ...
Unpacking libcrypt-dev:arm64 (1:4.4.27-1) ...
Selecting previously unselected package rpcsvc-proto.
Preparing to unpack .../030-rpcsvc-proto_1.4.2-0ubuntu6_arm64.deb ...
Unpacking rpcsvc-proto (1.4.2-0ubuntu6) ...
Selecting previously unselected package libtirpc-dev:arm64.
Preparing to unpack .../031-libtirpc-dev_1.3.2-2ubuntu0.1_arm64.deb ...
Unpacking libtirpc-dev:arm64 (1.3.2-2ubuntu0.1) ...
Selecting previously unselected package libnsl-dev:arm64.
Preparing to unpack .../032-libnsl-dev_1.3.0-2build2_arm64.deb ...
Unpacking libnsl-dev:arm64 (1.3.0-2build2) ...
Selecting previously unselected package libc6-dev:arm64.
Preparing to unpack .../033-libc6-dev_2.35-0ubuntu3.1_arm64.deb ...
Unpacking libc6-dev:arm64 (2.35-0ubuntu3.1) ...
Selecting previously unselected package gcc-11-base:arm64.
Preparing to unpack .../034-gcc-11-base_11.4.0-1ubuntu1~22.04_arm64.deb ...
Unpacking gcc-11-base:arm64 (11.4.0-1ubuntu1~22.04) ...
Selecting previously unselected package libisl23:arm64.
Preparing to unpack .../035-libisl23_0.24-2build1_arm64.deb ...
Unpacking libisl23:arm64 (0.24-2build1) ...
Selecting previously unselected package libmpfr6:arm64.
Preparing to unpack .../036-libmpfr6_4.1.0-3build3_arm64.deb ...
Unpacking libmpfr6:arm64 (4.1.0-3build3) ...
Selecting previously unselected package libmpc3:arm64.
Preparing to unpack .../037-libmpc3_1.2.1-2build1_arm64.deb ...
Unpacking libmpc3:arm64 (1.2.1-2build1) ...
Selecting previously unselected package cpp-11.
Preparing to unpack .../038-cpp-11_11.4.0-1ubuntu1~22.04_arm64.deb ...
Unpacking cpp-11 (11.4.0-1ubuntu1~22.04) ...
Selecting previously unselected package cpp.
Preparing to unpack .../039-cpp_4%3a11.2.0-1ubuntu1_arm64.deb ...
Unpacking cpp (4:11.2.0-1ubuntu1) ...
Selecting previously unselected package libcc1-0:arm64.
Preparing to unpack .../040-libcc1-0_12.3.0-1ubuntu1~22.04_arm64.deb ...
Unpacking libcc1-0:arm64 (12.3.0-1ubuntu1~22.04) ...
Selecting previously unselected package libgomp1:arm64.
Preparing to unpack .../041-libgomp1_12.3.0-1ubuntu1~22.04_arm64.deb ...
Unpacking libgomp1:arm64 (12.3.0-1ubuntu1~22.04) ...
Selecting previously unselected package libitm1:arm64.
Preparing to unpack .../042-libitm1_12.3.0-1ubuntu1~22.04_arm64.deb ...
Unpacking libitm1:arm64 (12.3.0-1ubuntu1~22.04) ...
Selecting previously unselected package libatomic1:arm64.
Preparing to unpack .../043-libatomic1_12.3.0-1ubuntu1~22.04_arm64.deb ...
Unpacking libatomic1:arm64 (12.3.0-1ubuntu1~22.04) ...
Selecting previously unselected package libasan6:arm64.
Preparing to unpack .../044-libasan6_11.4.0-1ubuntu1~22.04_arm64.deb ...
Unpacking libasan6:arm64 (11.4.0-1ubuntu1~22.04) ...
Selecting previously unselected package liblsan0:arm64.
Preparing to unpack .../045-liblsan0_12.3.0-1ubuntu1~22.04_arm64.deb ...
Unpacking liblsan0:arm64 (12.3.0-1ubuntu1~22.04) ...
Selecting previously unselected package libtsan0:arm64.
Preparing to unpack .../046-libtsan0_11.4.0-1ubuntu1~22.04_arm64.deb ...
Unpacking libtsan0:arm64 (11.4.0-1ubuntu1~22.04) ...
Selecting previously unselected package libubsan1:arm64.
Preparing to unpack .../047-libubsan1_12.3.0-1ubuntu1~22.04_arm64.deb ...
Unpacking libubsan1:arm64 (12.3.0-1ubuntu1~22.04) ...
Selecting previously unselected package libhwasan0:arm64.
Preparing to unpack .../048-libhwasan0_12.3.0-1ubuntu1~22.04_arm64.deb ...
Unpacking libhwasan0:arm64 (12.3.0-1ubuntu1~22.04) ...
Selecting previously unselected package libgcc-11-dev:arm64.
Preparing to unpack .../049-libgcc-11-dev_11.4.0-1ubuntu1~22.04_arm64.deb ...
Unpacking libgcc-11-dev:arm64 (11.4.0-1ubuntu1~22.04) ...
Selecting previously unselected package gcc-11.
Preparing to unpack .../050-gcc-11_11.4.0-1ubuntu1~22.04_arm64.deb ...
Unpacking gcc-11 (11.4.0-1ubuntu1~22.04) ...
Selecting previously unselected package gcc.
Preparing to unpack .../051-gcc_4%3a11.2.0-1ubuntu1_arm64.deb ...
Unpacking gcc (4:11.2.0-1ubuntu1) ...
Selecting previously unselected package libstdc++-11-dev:arm64.
Preparing to unpack .../052-libstdc++-11-dev_11.4.0-1ubuntu1~22.04_arm64.deb ...
Unpacking libstdc++-11-dev:arm64 (11.4.0-1ubuntu1~22.04) ...
Selecting previously unselected package g++-11.
Preparing to unpack .../053-g++-11_11.4.0-1ubuntu1~22.04_arm64.deb ...
Unpacking g++-11 (11.4.0-1ubuntu1~22.04) ...
Selecting previously unselected package g++.
Preparing to unpack .../054-g++_4%3a11.2.0-1ubuntu1_arm64.deb ...
Unpacking g++ (4:11.2.0-1ubuntu1) ...
Selecting previously unselected package make.
Preparing to unpack .../055-make_4.3-4.1build1_arm64.deb ...
Unpacking make (4.3-4.1build1) ...
Selecting previously unselected package libdpkg-perl.
Preparing to unpack .../056-libdpkg-perl_1.21.1ubuntu2.2_all.deb ...
Unpacking libdpkg-perl (1.21.1ubuntu2.2) ...
Selecting previously unselected package bzip2.
Preparing to unpack .../057-bzip2_1.0.8-5build1_arm64.deb ...
Unpacking bzip2 (1.0.8-5build1) ...
Selecting previously unselected package patch.
Preparing to unpack .../058-patch_2.7.6-7build2_arm64.deb ...
Unpacking patch (2.7.6-7build2) ...
Selecting previously unselected package lto-disabled-list.
Preparing to unpack .../059-lto-disabled-list_24_all.deb ...
Unpacking lto-disabled-list (24) ...
Selecting previously unselected package dpkg-dev.
Preparing to unpack .../060-dpkg-dev_1.21.1ubuntu2.2_all.deb ...
Unpacking dpkg-dev (1.21.1ubuntu2.2) ...
Selecting previously unselected package build-essential.
Preparing to unpack .../061-build-essential_12.9ubuntu3_arm64.deb ...
Unpacking build-essential (12.9ubuntu3) ...
Selecting previously unselected package libassuan0:arm64.
Preparing to unpack .../062-libassuan0_2.5.5-1build1_arm64.deb ...
Unpacking libassuan0:arm64 (2.5.5-1build1) ...
Selecting previously unselected package gpgconf.
Preparing to unpack .../063-gpgconf_2.2.27-3ubuntu2.1_arm64.deb ...
Unpacking gpgconf (2.2.27-3ubuntu2.1) ...
Selecting previously unselected package libksba8:arm64.
Preparing to unpack .../064-libksba8_1.6.0-2ubuntu0.2_arm64.deb ...
Unpacking libksba8:arm64 (1.6.0-2ubuntu0.2) ...
Selecting previously unselected package libsasl2-modules-db:arm64.
Preparing to unpack .../065-libsasl2-modules-db_2.1.27+dfsg2-3ubuntu1.2_arm64.deb ...
Unpacking libsasl2-modules-db:arm64 (2.1.27+dfsg2-3ubuntu1.2) ...
Selecting previously unselected package libsasl2-2:arm64.
Preparing to unpack .../066-libsasl2-2_2.1.27+dfsg2-3ubuntu1.2_arm64.deb ...
Unpacking libsasl2-2:arm64 (2.1.27+dfsg2-3ubuntu1.2) ...
Selecting previously unselected package libldap-2.5-0:arm64.
Preparing to unpack .../067-libldap-2.5-0_2.5.16+dfsg-0ubuntu0.22.04.1_arm64.deb ...
Unpacking libldap-2.5-0:arm64 (2.5.16+dfsg-0ubuntu0.22.04.1) ...
Selecting previously unselected package libnpth0:arm64.
Preparing to unpack .../068-libnpth0_1.6-3build2_arm64.deb ...
Unpacking libnpth0:arm64 (1.6-3build2) ...
Selecting previously unselected package dirmngr.
Preparing to unpack .../069-dirmngr_2.2.27-3ubuntu2.1_arm64.deb ...
Unpacking dirmngr (2.2.27-3ubuntu2.1) ...
Selecting previously unselected package libfakeroot:arm64.
Preparing to unpack .../070-libfakeroot_1.28-1ubuntu1_arm64.deb ...
Unpacking libfakeroot:arm64 (1.28-1ubuntu1) ...
Selecting previously unselected package fakeroot.
Preparing to unpack .../071-fakeroot_1.28-1ubuntu1_arm64.deb ...
Unpacking fakeroot (1.28-1ubuntu1) ...
Selecting previously unselected package fonts-dejavu-core.
Preparing to unpack .../072-fonts-dejavu-core_2.37-2build1_all.deb ...
Unpacking fonts-dejavu-core (2.37-2build1) ...
Selecting previously unselected package fontconfig-config.
Preparing to unpack .../073-fontconfig-config_2.13.1-4.2ubuntu5_all.deb ...
Unpacking fontconfig-config (2.13.1-4.2ubuntu5) ...
Selecting previously unselected package gnupg-l10n.
Preparing to unpack .../074-gnupg-l10n_2.2.27-3ubuntu2.1_all.deb ...
Unpacking gnupg-l10n (2.2.27-3ubuntu2.1) ...
Selecting previously unselected package gnupg-utils.
Preparing to unpack .../075-gnupg-utils_2.2.27-3ubuntu2.1_arm64.deb ...
Unpacking gnupg-utils (2.2.27-3ubuntu2.1) ...
Selecting previously unselected package gpg.
Preparing to unpack .../076-gpg_2.2.27-3ubuntu2.1_arm64.deb ...
Unpacking gpg (2.2.27-3ubuntu2.1) ...
Selecting previously unselected package pinentry-curses.
Preparing to unpack .../077-pinentry-curses_1.1.1-1build2_arm64.deb ...
Unpacking pinentry-curses (1.1.1-1build2) ...
Selecting previously unselected package gpg-agent.
Preparing to unpack .../078-gpg-agent_2.2.27-3ubuntu2.1_arm64.deb ...
Unpacking gpg-agent (2.2.27-3ubuntu2.1) ...
Selecting previously unselected package gpg-wks-client.
Preparing to unpack .../079-gpg-wks-client_2.2.27-3ubuntu2.1_arm64.deb ...
Unpacking gpg-wks-client (2.2.27-3ubuntu2.1) ...
Selecting previously unselected package gpg-wks-server.
Preparing to unpack .../080-gpg-wks-server_2.2.27-3ubuntu2.1_arm64.deb ...
Unpacking gpg-wks-server (2.2.27-3ubuntu2.1) ...
Selecting previously unselected package gpgsm.
Preparing to unpack .../081-gpgsm_2.2.27-3ubuntu2.1_arm64.deb ...
Unpacking gpgsm (2.2.27-3ubuntu2.1) ...
Selecting previously unselected package gnupg.
Preparing to unpack .../082-gnupg_2.2.27-3ubuntu2.1_all.deb ...
Unpacking gnupg (2.2.27-3ubuntu2.1) ...
Selecting previously unselected package javascript-common.
Preparing to unpack .../083-javascript-common_11+nmu1_all.deb ...
Unpacking javascript-common (11+nmu1) ...
Selecting previously unselected package libalgorithm-diff-perl.
Preparing to unpack .../084-libalgorithm-diff-perl_1.201-1_all.deb ...
Unpacking libalgorithm-diff-perl (1.201-1) ...
Selecting previously unselected package libalgorithm-diff-xs-perl.
Preparing to unpack .../085-libalgorithm-diff-xs-perl_0.04-6build3_arm64.deb ...
Unpacking libalgorithm-diff-xs-perl (0.04-6build3) ...
Selecting previously unselected package libalgorithm-merge-perl.
Preparing to unpack .../086-libalgorithm-merge-perl_0.08-3_all.deb ...
Unpacking libalgorithm-merge-perl (0.08-3) ...
Selecting previously unselected package libbrotli1:arm64.
Preparing to unpack .../087-libbrotli1_1.0.9-2build6_arm64.deb ...
Unpacking libbrotli1:arm64 (1.0.9-2build6) ...
Selecting previously unselected package libfreetype6:arm64.
Preparing to unpack .../088-libfreetype6_2.11.1+dfsg-1ubuntu0.2_arm64.deb ...
Unpacking libfreetype6:arm64 (2.11.1+dfsg-1ubuntu0.2) ...
Selecting previously unselected package libfontconfig1:arm64.
Preparing to unpack .../089-libfontconfig1_2.13.1-4.2ubuntu5_arm64.deb ...
Unpacking libfontconfig1:arm64 (2.13.1-4.2ubuntu5) ...
Selecting previously unselected package libjpeg-turbo8:arm64.
Preparing to unpack .../090-libjpeg-turbo8_2.1.2-0ubuntu1_arm64.deb ...
Unpacking libjpeg-turbo8:arm64 (2.1.2-0ubuntu1) ...
Selecting previously unselected package libjpeg8:arm64.
Preparing to unpack .../091-libjpeg8_8c-2ubuntu10_arm64.deb ...
Unpacking libjpeg8:arm64 (8c-2ubuntu10) ...
Selecting previously unselected package libdeflate0:arm64.
Preparing to unpack .../092-libdeflate0_1.10-2_arm64.deb ...
Unpacking libdeflate0:arm64 (1.10-2) ...
Selecting previously unselected package libjbig0:arm64.
Preparing to unpack .../093-libjbig0_2.1-3.1ubuntu0.22.04.1_arm64.deb ...
Unpacking libjbig0:arm64 (2.1-3.1ubuntu0.22.04.1) ...
Selecting previously unselected package libwebp7:arm64.
Preparing to unpack .../094-libwebp7_1.2.2-2ubuntu0.22.04.1_arm64.deb ...
Unpacking libwebp7:arm64 (1.2.2-2ubuntu0.22.04.1) ...
Selecting previously unselected package libtiff5:arm64.
Preparing to unpack .../095-libtiff5_4.3.0-6ubuntu0.5_arm64.deb ...
Unpacking libtiff5:arm64 (4.3.0-6ubuntu0.5) ...
Selecting previously unselected package libxpm4:arm64.
Preparing to unpack .../096-libxpm4_1%3a3.5.12-1ubuntu0.22.04.1_arm64.deb ...
Unpacking libxpm4:arm64 (1:3.5.12-1ubuntu0.22.04.1) ...
Selecting previously unselected package libgd3:arm64.
Preparing to unpack .../097-libgd3_2.3.0-2ubuntu2_arm64.deb ...
Unpacking libgd3:arm64 (2.3.0-2ubuntu2) ...
Selecting previously unselected package libc-devtools.
Preparing to unpack .../098-libc-devtools_2.35-0ubuntu3.1_arm64.deb ...
Unpacking libc-devtools (2.35-0ubuntu3.1) ...
Selecting previously unselected package libexpat1-dev:arm64.
Preparing to unpack .../099-libexpat1-dev_2.4.7-1ubuntu0.2_arm64.deb ...
Unpacking libexpat1-dev:arm64 (2.4.7-1ubuntu0.2) ...
Selecting previously unselected package libfile-fcntllock-perl.
Preparing to unpack .../100-libfile-fcntllock-perl_0.22-3build7_arm64.deb ...
Unpacking libfile-fcntllock-perl (0.22-3build7) ...
Selecting previously unselected package libjs-jquery.
Preparing to unpack .../101-libjs-jquery_3.6.0+dfsg+~3.5.13-1_all.deb ...
Unpacking libjs-jquery (3.6.0+dfsg+~3.5.13-1) ...
Selecting previously unselected package libjs-underscore.
Preparing to unpack .../102-libjs-underscore_1.13.2~dfsg-2_all.deb ...
Unpacking libjs-underscore (1.13.2~dfsg-2) ...
Selecting previously unselected package libjs-sphinxdoc.
Preparing to unpack .../103-libjs-sphinxdoc_4.3.2-1_all.deb ...
Unpacking libjs-sphinxdoc (4.3.2-1) ...
Selecting previously unselected package libldap-common.
Preparing to unpack .../104-libldap-common_2.5.16+dfsg-0ubuntu0.22.04.1_all.deb ...
Unpacking libldap-common (2.5.16+dfsg-0ubuntu0.22.04.1) ...
Selecting previously unselected package libpython3.10:arm64.
Preparing to unpack .../105-libpython3.10_3.10.12-1~22.04.2_arm64.deb ...
Unpacking libpython3.10:arm64 (3.10.12-1~22.04.2) ...
Selecting previously unselected package zlib1g-dev:arm64.
Preparing to unpack .../106-zlib1g-dev_1%3a1.2.11.dfsg-2ubuntu9.2_arm64.deb ...
Unpacking zlib1g-dev:arm64 (1:1.2.11.dfsg-2ubuntu9.2) ...
Selecting previously unselected package libpython3.10-dev:arm64.
Preparing to unpack .../107-libpython3.10-dev_3.10.12-1~22.04.2_arm64.deb ...
Unpacking libpython3.10-dev:arm64 (3.10.12-1~22.04.2) ...
Selecting previously unselected package libpython3-dev:arm64.
Preparing to unpack .../108-libpython3-dev_3.10.6-1~22.04_arm64.deb ...
Unpacking libpython3-dev:arm64 (3.10.6-1~22.04) ...
Selecting previously unselected package libsasl2-modules:arm64.
Preparing to unpack .../109-libsasl2-modules_2.1.27+dfsg2-3ubuntu1.2_arm64.deb ...
Unpacking libsasl2-modules:arm64 (2.1.27+dfsg2-3ubuntu1.2) ...
Selecting previously unselected package manpages-dev.
Preparing to unpack .../110-manpages-dev_5.10-1ubuntu1_all.deb ...
Unpacking manpages-dev (5.10-1ubuntu1) ...
Selecting previously unselected package python3.10-dev.
Preparing to unpack .../111-python3.10-dev_3.10.12-1~22.04.2_arm64.deb ...
Unpacking python3.10-dev (3.10.12-1~22.04.2) ...
Selecting previously unselected package python3-lib2to3.
Preparing to unpack .../112-python3-lib2to3_3.10.8-1~22.04_all.deb ...
Unpacking python3-lib2to3 (3.10.8-1~22.04) ...
Selecting previously unselected package python3-distutils.
Preparing to unpack .../113-python3-distutils_3.10.8-1~22.04_all.deb ...
Unpacking python3-distutils (3.10.8-1~22.04) ...
Selecting previously unselected package python3-dev.
Preparing to unpack .../114-python3-dev_3.10.6-1~22.04_arm64.deb ...
Unpacking python3-dev (3.10.6-1~22.04) ...
Selecting previously unselected package python3-setuptools.
Preparing to unpack .../115-python3-setuptools_59.6.0-1.2ubuntu0.22.04.1_all.deb ...
Unpacking python3-setuptools (59.6.0-1.2ubuntu0.22.04.1) ...
Selecting previously unselected package python3-wheel.
Preparing to unpack .../116-python3-wheel_0.37.1-2ubuntu0.22.04.1_all.deb ...
Unpacking python3-wheel (0.37.1-2ubuntu0.22.04.1) ...
Selecting previously unselected package python3-pip.
Preparing to unpack .../117-python3-pip_22.0.2+dfsg-1ubuntu0.3_all.deb ...
Unpacking python3-pip (22.0.2+dfsg-1ubuntu0.3) ...
Setting up libksba8:arm64 (1.6.0-2ubuntu0.2) ...
Setting up media-types (7.0.0) ...
Setting up javascript-common (11+nmu1) ...
Setting up gcc-11-base:arm64 (11.4.0-1ubuntu1~22.04) ...
Setting up libxau6:arm64 (1:1.0.9-1build5) ...
Setting up lto-disabled-list (24) ...
Setting up manpages (5.10-1ubuntu1) ...
Setting up libbrotli1:arm64 (1.0.9-2build6) ...
Setting up libsqlite3-0:arm64 (3.37.2-2ubuntu0.1) ...
Setting up libsasl2-modules:arm64 (2.1.27+dfsg2-3ubuntu1.2) ...
Setting up binutils-common:arm64 (2.38-4ubuntu2.3) ...
Setting up libdeflate0:arm64 (1.10-2) ...
Setting up linux-libc-dev:arm64 (5.15.0-79.86) ...
Setting up libctf-nobfd0:arm64 (2.38-4ubuntu2.3) ...
Setting up libnpth0:arm64 (1.6-3build2) ...
Setting up libassuan0:arm64 (2.5.5-1build1) ...
Setting up libgomp1:arm64 (12.3.0-1ubuntu1~22.04) ...
Setting up perl-modules-5.34 (5.34.0-3ubuntu1.2) ...
Setting up bzip2 (1.0.8-5build1) ...
Setting up libldap-common (2.5.16+dfsg-0ubuntu0.22.04.1) ...
Setting up libjbig0:arm64 (2.1-3.1ubuntu0.22.04.1) ...
Setting up libfakeroot:arm64 (1.28-1ubuntu1) ...
Setting up libasan6:arm64 (11.4.0-1ubuntu1~22.04) ...
Setting up libsasl2-modules-db:arm64 (2.1.27+dfsg2-3ubuntu1.2) ...
Setting up fakeroot (1.28-1ubuntu1) ...
update-alternatives: using /usr/bin/fakeroot-sysv to provide /usr/bin/fakeroot (fakeroot) in auto mode
update-alternatives: warning: skip creation of /usr/share/man/man1/fakeroot.1.gz because associated file /usr/share/man/man1/fakeroot-sysv.1.gz (of link group fakeroot) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/man1/faked.1.gz because associated file /usr/share/man/man1/faked-sysv.1.gz (of link group fakeroot) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/es/man1/fakeroot.1.gz because associated file /usr/share/man/es/man1/fakeroot-sysv.1.gz (of link group fakeroot) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/es/man1/faked.1.gz because associated file /usr/share/man/es/man1/faked-sysv.1.gz (of link group fakeroot) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/fr/man1/fakeroot.1.gz because associated file /usr/share/man/fr/man1/fakeroot-sysv.1.gz (of link group fakeroot) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/fr/man1/faked.1.gz because associated file /usr/share/man/fr/man1/faked-sysv.1.gz (of link group fakeroot) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/sv/man1/fakeroot.1.gz because associated file /usr/share/man/sv/man1/fakeroot-sysv.1.gz (of link group fakeroot) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/sv/man1/faked.1.gz because associated file /usr/share/man/sv/man1/faked-sysv.1.gz (of link group fakeroot) doesn't exist
Setting up libtirpc-dev:arm64 (1.3.2-2ubuntu0.1) ...
Setting up rpcsvc-proto (1.4.2-0ubuntu6) ...
Setting up libx11-data (2:1.7.5-1ubuntu0.2) ...
Setting up make (4.3-4.1build1) ...
Setting up libmpfr6:arm64 (4.1.0-3build3) ...
Setting up gnupg-l10n (2.2.27-3ubuntu2.1) ...
Setting up xz-utils (5.2.5-2ubuntu1) ...
update-alternatives: using /usr/bin/xz to provide /usr/bin/lzma (lzma) in auto mode
update-alternatives: warning: skip creation of /usr/share/man/man1/lzma.1.gz because associated file /usr/share/man/man1/xz.1.gz (of link group lzma) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/man1/unlzma.1.gz because associated file /usr/share/man/man1/unxz.1.gz (of link group lzma) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/man1/lzcat.1.gz because associated file /usr/share/man/man1/xzcat.1.gz (of link group lzma) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/man1/lzmore.1.gz because associated file /usr/share/man/man1/xzmore.1.gz (of link group lzma) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/man1/lzless.1.gz because associated file /usr/share/man/man1/xzless.1.gz (of link group lzma) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/man1/lzdiff.1.gz because associated file /usr/share/man/man1/xzdiff.1.gz (of link group lzma) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/man1/lzcmp.1.gz because associated file /usr/share/man/man1/xzcmp.1.gz (of link group lzma) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/man1/lzgrep.1.gz because associated file /usr/share/man/man1/xzgrep.1.gz (of link group lzma) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/man1/lzegrep.1.gz because associated file /usr/share/man/man1/xzegrep.1.gz (of link group lzma) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/man1/lzfgrep.1.gz because associated file /usr/share/man/man1/xzfgrep.1.gz (of link group lzma) doesn't exist
Setting up libpng16-16:arm64 (1.6.37-3build5) ...
Setting up libmpc3:arm64 (1.2.1-2build1) ...
Setting up libatomic1:arm64 (12.3.0-1ubuntu1~22.04) ...
Setting up patch (2.7.6-7build2) ...
Setting up fonts-dejavu-core (2.37-2build1) ...
Setting up ucf (3.0043) ...
debconf: unable to initialize frontend: Dialog
debconf: (No usable dialog-like program is installed, so the dialog based frontend cannot be used. at /usr/share/perl5/Debconf/FrontEnd/Dialog.pm line 78.)
debconf: falling back to frontend: Readline
Setting up libjpeg-turbo8:arm64 (2.1.2-0ubuntu1) ...
Setting up libsasl2-2:arm64 (2.1.27+dfsg2-3ubuntu1.2) ...
Setting up libwebp7:arm64 (1.2.2-2ubuntu0.22.04.1) ...
Setting up libubsan1:arm64 (12.3.0-1ubuntu1~22.04) ...
Setting up libmd0:arm64 (1.0.4-1build1) ...
Setting up libnsl-dev:arm64 (1.3.0-2build2) ...
Setting up libhwasan0:arm64 (12.3.0-1ubuntu1~22.04) ...
Setting up libcrypt-dev:arm64 (1:4.4.27-1) ...
Setting up libmpdec3:arm64 (2.5.1-2build2) ...
Setting up netbase (6.3) ...
Setting up libjs-jquery (3.6.0+dfsg+~3.5.13-1) ...
Setting up libbinutils:arm64 (2.38-4ubuntu2.3) ...
Setting up libisl23:arm64 (0.24-2build1) ...
Setting up libc-dev-bin (2.35-0ubuntu3.1) ...
Setting up openssl (3.0.2-0ubuntu1.10) ...
Setting up libbsd0:arm64 (0.11.5-1) ...
Setting up readline-common (8.1.2-1) ...
Setting up libcc1-0:arm64 (12.3.0-1ubuntu1~22.04) ...
Setting up liblocale-gettext-perl (1.07-4build3) ...
Setting up liblsan0:arm64 (12.3.0-1ubuntu1~22.04) ...
Setting up libitm1:arm64 (12.3.0-1ubuntu1~22.04) ...
Setting up libgdbm6:arm64 (1.23-1) ...
Setting up libjs-underscore (1.13.2~dfsg-2) ...
Setting up libtsan0:arm64 (11.4.0-1ubuntu1~22.04) ...
Setting up libctf0:arm64 (2.38-4ubuntu2.3) ...
Setting up libjpeg8:arm64 (8c-2ubuntu10) ...
Setting up pinentry-curses (1.1.1-1build2) ...
Setting up cpp-11 (11.4.0-1ubuntu1~22.04) ...
Setting up manpages-dev (5.10-1ubuntu1) ...
Setting up libxdmcp6:arm64 (1:1.1.3-0ubuntu5) ...
Setting up libxcb1:arm64 (1.14-3ubuntu3) ...
Setting up fontconfig-config (2.13.1-4.2ubuntu5) ...
Setting up libreadline8:arm64 (8.1.2-1) ...
Setting up binutils-aarch64-linux-gnu (2.38-4ubuntu2.3) ...
Setting up binutils (2.38-4ubuntu2.3) ...
Setting up libldap-2.5-0:arm64 (2.5.16+dfsg-0ubuntu0.22.04.1) ...
Setting up libpython3.10-stdlib:arm64 (3.10.12-1~22.04.2) ...
Setting up ca-certificates (20230311ubuntu0.22.04.1) ...
debconf: unable to initialize frontend: Dialog
debconf: (No usable dialog-like program is installed, so the dialog based frontend cannot be used. at /usr/share/perl5/Debconf/FrontEnd/Dialog.pm line 78.)
debconf: falling back to frontend: Readline
Updating certificates in /etc/ssl/certs...
137 added, 0 removed; done.
Setting up libfreetype6:arm64 (2.11.1+dfsg-1ubuntu0.2) ...
Setting up libgdbm-compat4:arm64 (1.23-1) ...
Setting up libjs-sphinxdoc (4.3.2-1) ...
Setting up libgcc-11-dev:arm64 (11.4.0-1ubuntu1~22.04) ...
Setting up gcc-11 (11.4.0-1ubuntu1~22.04) ...
Setting up cpp (4:11.2.0-1ubuntu1) ...
Setting up gpgconf (2.2.27-3ubuntu2.1) ...
Setting up libc6-dev:arm64 (2.35-0ubuntu3.1) ...
Setting up libx11-6:arm64 (2:1.7.5-1ubuntu0.2) ...
Setting up libtiff5:arm64 (4.3.0-6ubuntu0.5) ...
Setting up libfontconfig1:arm64 (2.13.1-4.2ubuntu5) ...
Setting up gpg (2.2.27-3ubuntu2.1) ...
Setting up libpython3-stdlib:arm64 (3.10.6-1~22.04) ...
Setting up gnupg-utils (2.2.27-3ubuntu2.1) ...
Setting up libpython3.10:arm64 (3.10.12-1~22.04.2) ...
Setting up libperl5.34:arm64 (5.34.0-3ubuntu1.2) ...
Setting up gpg-agent (2.2.27-3ubuntu2.1) ...
Setting up python3.10 (3.10.12-1~22.04.2) ...
Setting up libxpm4:arm64 (1:3.5.12-1ubuntu0.22.04.1) ...
Setting up gpgsm (2.2.27-3ubuntu2.1) ...
Setting up python3 (3.10.6-1~22.04) ...
running python rtupdate hooks for python3.10...
running python post-rtupdate hooks for python3.10...
Setting up gcc (4:11.2.0-1ubuntu1) ...
Setting up dirmngr (2.2.27-3ubuntu2.1) ...
Setting up perl (5.34.0-3ubuntu1.2) ...
Setting up libexpat1-dev:arm64 (2.4.7-1ubuntu0.2) ...
Setting up libgd3:arm64 (2.3.0-2ubuntu2) ...
Setting up libdpkg-perl (1.21.1ubuntu2.2) ...
Setting up libstdc++-11-dev:arm64 (11.4.0-1ubuntu1~22.04) ...
Setting up gpg-wks-server (2.2.27-3ubuntu2.1) ...
Setting up zlib1g-dev:arm64 (1:1.2.11.dfsg-2ubuntu9.2) ...
Setting up python3-lib2to3 (3.10.8-1~22.04) ...
Setting up libc-devtools (2.35-0ubuntu3.1) ...
Setting up python3-pkg-resources (59.6.0-1.2ubuntu0.22.04.1) ...
Setting up python3-distutils (3.10.8-1~22.04) ...
Setting up python3-setuptools (59.6.0-1.2ubuntu0.22.04.1) ...
Setting up gpg-wks-client (2.2.27-3ubuntu2.1) ...
Setting up g++-11 (11.4.0-1ubuntu1~22.04) ...
Setting up libfile-fcntllock-perl (0.22-3build7) ...
Setting up libalgorithm-diff-perl (1.201-1) ...
Setting up python3-wheel (0.37.1-2ubuntu0.22.04.1) ...
Setting up dpkg-dev (1.21.1ubuntu2.2) ...
Setting up libpython3.10-dev:arm64 (3.10.12-1~22.04.2) ...
Setting up python3-pip (22.0.2+dfsg-1ubuntu0.3) ...
Setting up python3.10-dev (3.10.12-1~22.04.2) ...
Setting up g++ (4:11.2.0-1ubuntu1) ...
update-alternatives: using /usr/bin/g++ to provide /usr/bin/c++ (c++) in auto mode
update-alternatives: warning: skip creation of /usr/share/man/man1/c++.1.gz because associated file /usr/share/man/man1/g++.1.gz (of link group c++) doesn't exist
Setting up gnupg (2.2.27-3ubuntu2.1) ...
Setting up build-essential (12.9ubuntu3) ...
Setting up libalgorithm-diff-xs-perl (0.04-6build3) ...
Setting up libalgorithm-merge-perl (0.08-3) ...
Setting up libpython3-dev:arm64 (3.10.6-1~22.04) ...
Setting up python3-dev (3.10.6-1~22.04) ...
Processing triggers for libc-bin (2.35-0ubuntu3.1) ...
Processing triggers for ca-certificates (20230311ubuntu0.22.04.1) ...
Updating certificates in /etc/ssl/certs...
0 added, 0 removed; done.
Running hooks in /etc/ca-certificates/update.d...
done.
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# pip3 install psycopg2-binary
Collecting psycopg2-binary
  Downloading psycopg2_binary-2.9.7-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl (2.8 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 2.8/2.8 MB 274.6 kB/s eta 0:00:00
Installing collected packages: psycopg2-binary
Successfully installed psycopg2-binary-2.9.7
WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# pip3 install apache-airflow
Collecting apache-airflow
  Downloading apache_airflow-2.7.0-py3-none-any.whl (12.9 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 12.9/12.9 MB 178.4 kB/s eta 0:00:00
Collecting setproctitle>=1.1.8
  Downloading setproctitle-1.3.2-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl (31 kB)
Collecting pygments>=2.0.1
  Downloading Pygments-2.16.1-py3-none-any.whl (1.2 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 1.2/1.2 MB 67.6 kB/s eta 0:00:00
Collecting rich-argparse>=1.0.0
  Downloading rich_argparse-1.3.0-py3-none-any.whl (17 kB)
Collecting asgiref
  Downloading asgiref-3.7.2-py3-none-any.whl (24 kB)
Collecting opentelemetry-api==1.15.0
  Downloading opentelemetry_api-1.15.0-py3-none-any.whl (56 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 56.5/56.5 KB 195.0 kB/s eta 0:00:00
Collecting croniter>=0.3.17
  Downloading croniter-1.4.1-py2.py3-none-any.whl (19 kB)
Collecting tabulate>=0.7.5
  Downloading tabulate-0.9.0-py3-none-any.whl (35 kB)
Collecting apache-airflow-providers-imap
  Downloading apache_airflow_providers_imap-3.3.0-py3-none-any.whl (17 kB)
Collecting dill>=0.2.2
  Downloading dill-0.3.7-py3-none-any.whl (115 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 115.3/115.3 KB 276.0 kB/s eta 0:00:00
Collecting rfc3339-validator>=0.1.4
  Downloading rfc3339_validator-0.1.4-py2.py3-none-any.whl (3.5 kB)
Collecting jinja2>=3.0.0
  Downloading Jinja2-3.1.2-py3-none-any.whl (133 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 133.1/133.1 KB 140.1 kB/s eta 0:00:00
Collecting linkify-it-py>=2.0.0
  Downloading linkify_it_py-2.0.2-py3-none-any.whl (19 kB)
Collecting configupdater>=3.1.1
  Downloading ConfigUpdater-3.1.1-py2.py3-none-any.whl (34 kB)
Collecting markupsafe>=1.1.1
  Downloading MarkupSafe-2.1.3-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl (26 kB)
Collecting alembic<2.0,>=1.6.3
  Downloading alembic-1.11.3-py3-none-any.whl (225 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 225.4/225.4 KB 142.8 kB/s eta 0:00:00
Collecting pluggy>=1.0
  Downloading pluggy-1.2.0-py3-none-any.whl (17 kB)
Collecting graphviz>=0.12
  Downloading graphviz-0.20.1-py3-none-any.whl (47 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 47.0/47.0 KB 103.3 kB/s eta 0:00:00
Collecting blinker
  Downloading blinker-1.6.2-py3-none-any.whl (13 kB)
Collecting markdown>=3.0
  Downloading Markdown-3.4.4-py3-none-any.whl (94 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 94.2/94.2 KB 74.8 kB/s eta 0:00:00
Collecting gunicorn>=20.1.0
  Downloading gunicorn-21.2.0-py3-none-any.whl (80 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 80.2/80.2 KB 149.2 kB/s eta 0:00:00
Collecting python-slugify>=5.0
  Downloading python_slugify-8.0.1-py2.py3-none-any.whl (9.7 kB)
Collecting psutil>=4.2.0
  Downloading psutil-5.9.5.tar.gz (493 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 493.5/493.5 KB 145.9 kB/s eta 0:00:00
  Installing build dependencies ... done
  Getting requirements to build wheel ... done
  Preparing metadata (pyproject.toml) ... done
Collecting lockfile>=0.12.2
  Downloading lockfile-0.12.2-py2.py3-none-any.whl (13 kB)
Collecting pathspec>=0.9.0
  Downloading pathspec-0.11.2-py3-none-any.whl (29 kB)
Collecting lazy-object-proxy
  Downloading lazy_object_proxy-1.9.0-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl (64 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 64.1/64.1 KB 240.4 kB/s eta 0:00:00
Collecting sqlalchemy<2.0,>=1.4
  Downloading SQLAlchemy-1.4.49-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl (1.6 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 1.6/1.6 MB 184.8 kB/s eta 0:00:00
Collecting flask-login>=0.6.2
  Downloading Flask_Login-0.6.2-py3-none-any.whl (17 kB)
Collecting attrs>=22.1.0
  Downloading attrs-23.1.0-py3-none-any.whl (61 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 61.2/61.2 KB 266.7 kB/s eta 0:00:00
Collecting mdit-py-plugins>=0.3.0
  Downloading mdit_py_plugins-0.4.0-py3-none-any.whl (54 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 54.1/54.1 KB 188.4 kB/s eta 0:00:00
Collecting werkzeug>=2.0
  Downloading werkzeug-2.3.7-py3-none-any.whl (242 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 242.2/242.2 KB 159.5 kB/s eta 0:00:00
Collecting opentelemetry-exporter-otlp
  Downloading opentelemetry_exporter_otlp-1.19.0-py3-none-any.whl (7.0 kB)
Collecting httpx
  Downloading httpx-0.24.1-py3-none-any.whl (75 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 75.4/75.4 KB 198.8 kB/s eta 0:00:00
Collecting sqlalchemy-jsonfield>=1.0
  Downloading SQLAlchemy_JSONField-1.0.1.post0-py3-none-any.whl (10 kB)
Collecting apache-airflow-providers-ftp
  Downloading apache_airflow_providers_ftp-3.5.0-py3-none-any.whl (18 kB)
Collecting python-dateutil>=2.3
  Downloading python_dateutil-2.8.2-py2.py3-none-any.whl (247 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 247.7/247.7 KB 230.2 kB/s eta 0:00:00
Collecting google-re2>=1.0
  Downloading google_re2-1.1-1-cp310-cp310-manylinux_2_24_aarch64.manylinux_2_28_aarch64.whl (503 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 503.5/503.5 KB 201.8 kB/s eta 0:00:00
Collecting marshmallow-oneofschema>=2.0.1
  Downloading marshmallow_oneofschema-3.0.1-py2.py3-none-any.whl (5.8 kB)
Collecting packaging>=14.0
  Downloading packaging-23.1-py3-none-any.whl (48 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 48.9/48.9 KB 273.7 kB/s eta 0:00:00
Collecting unicodecsv>=0.14.1
  Downloading unicodecsv-0.14.1.tar.gz (10 kB)
  Preparing metadata (setup.py) ... done
Collecting apache-airflow-providers-http
  Downloading apache_airflow_providers_http-4.5.0-py3-none-any.whl (23 kB)
Collecting cryptography>=0.9.3
  Downloading cryptography-41.0.3-cp37-abi3-manylinux_2_28_aarch64.whl (4.1 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 4.1/4.1 MB 198.0 kB/s eta 0:00:00
Collecting argcomplete>=1.10
  Downloading argcomplete-3.1.1-py3-none-any.whl (41 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 41.5/41.5 KB 139.6 kB/s eta 0:00:00
Collecting itsdangerous>=2.0
  Downloading itsdangerous-2.1.2-py3-none-any.whl (15 kB)
Collecting markdown-it-py>=2.1.0
  Downloading markdown_it_py-3.0.0-py3-none-any.whl (87 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 87.5/87.5 KB 183.2 kB/s eta 0:00:00
Collecting flask-caching>=1.5.0
  Downloading Flask_Caching-2.0.2-py3-none-any.whl (28 kB)
Collecting python-daemon>=3.0.0
  Downloading python_daemon-3.0.1-py3-none-any.whl (31 kB)
Collecting flask-appbuilder==4.3.3
  Downloading Flask_AppBuilder-4.3.3-py3-none-any.whl (2.5 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 2.5/2.5 MB 204.5 kB/s eta 0:00:00
Collecting pydantic<2.0.0,>=1.10.0
  Downloading pydantic-1.10.12-py3-none-any.whl (158 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 158.4/158.4 KB 180.1 kB/s eta 0:00:00
Collecting apache-airflow-providers-common-sql
  Downloading apache_airflow_providers_common_sql-1.7.0-py3-none-any.whl (31 kB)
Collecting apache-airflow-providers-sqlite
  Downloading apache_airflow_providers_sqlite-3.4.3-py3-none-any.whl (13 kB)
Collecting typing-extensions>=4.0.0
  Downloading typing_extensions-4.7.1-py3-none-any.whl (33 kB)
Collecting connexion[flask]>=2.10.0
  Downloading connexion-2.14.2-py2.py3-none-any.whl (95 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 95.1/95.1 KB 217.2 kB/s eta 0:00:00
Collecting cattrs>=22.1.0
  Downloading cattrs-23.1.2-py3-none-any.whl (50 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 50.8/50.8 KB 190.0 kB/s eta 0:00:00
Collecting pyjwt>=2.0.0
  Downloading PyJWT-2.8.0-py3-none-any.whl (22 kB)
Collecting colorlog<5.0,>=4.0.2
  Downloading colorlog-4.8.0-py2.py3-none-any.whl (10 kB)
Collecting flask-session>=0.4.0
  Downloading flask_session-0.5.0-py3-none-any.whl (7.2 kB)
Collecting cron-descriptor>=1.2.24
  Downloading cron_descriptor-1.4.0.tar.gz (29 kB)
  Preparing metadata (setup.py) ... done
Collecting rich>=12.4.4
  Downloading rich-13.5.2-py3-none-any.whl (239 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 239.7/239.7 KB 171.2 kB/s eta 0:00:00
Collecting deprecated>=1.2.13
  Downloading Deprecated-1.2.14-py2.py3-none-any.whl (9.6 kB)
Collecting tenacity!=8.2.0,>=6.2.0
  Downloading tenacity-8.2.3-py3-none-any.whl (24 kB)
Collecting pendulum>=2.0
  Downloading pendulum-2.1.2.tar.gz (81 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 81.2/81.2 KB 142.3 kB/s eta 0:00:00
  Installing build dependencies ... done
  Getting requirements to build wheel ... done
  Preparing metadata (pyproject.toml) ... done
Collecting python-nvd3>=0.15.0
  Downloading python-nvd3-0.15.0.tar.gz (31 kB)
  Preparing metadata (setup.py) ... done
Collecting flask-wtf>=0.15
  Downloading Flask_WTF-1.1.1-py3-none-any.whl (12 kB)
Collecting flask<2.3,>=2.2
  Downloading Flask-2.2.5-py3-none-any.whl (101 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 101.8/101.8 KB 133.0 kB/s eta 0:00:00
Collecting termcolor>=1.1.0
  Downloading termcolor-2.3.0-py3-none-any.whl (6.9 kB)
Collecting jsonschema>=4.18.0
  Downloading jsonschema-4.19.0-py3-none-any.whl (83 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 83.4/83.4 KB 196.8 kB/s eta 0:00:00
Collecting apispec[yaml]<7,>=6.0.0
  Downloading apispec-6.3.0-py3-none-any.whl (29 kB)
Collecting sqlalchemy-utils<1,>=0.32.21
  Downloading SQLAlchemy_Utils-0.41.1-py3-none-any.whl (92 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 92.6/92.6 KB 284.6 kB/s eta 0:00:00
Collecting email-validator<2,>=1.0.5
  Downloading email_validator-1.3.1-py2.py3-none-any.whl (22 kB)
Collecting prison<1.0.0,>=0.2.1
  Downloading prison-0.2.1-py2.py3-none-any.whl (5.8 kB)
Collecting Flask-JWT-Extended<5.0.0,>=4.0.0
  Downloading Flask_JWT_Extended-4.5.2-py2.py3-none-any.whl (22 kB)
Collecting marshmallow-sqlalchemy<0.27.0,>=0.22.0
  Downloading marshmallow_sqlalchemy-0.26.1-py2.py3-none-any.whl (15 kB)
Collecting Flask-Limiter<4,>3
  Downloading Flask_Limiter-3.4.0-py3-none-any.whl (28 kB)
Collecting Flask-SQLAlchemy<3,>=2.4
  Downloading Flask_SQLAlchemy-2.5.1-py2.py3-none-any.whl (17 kB)
Collecting WTForms<4
  Downloading WTForms-3.0.1-py3-none-any.whl (136 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 136.5/136.5 KB 232.5 kB/s eta 0:00:00
Collecting colorama<1,>=0.3.9
  Downloading colorama-0.4.6-py2.py3-none-any.whl (25 kB)
Collecting click<9,>=8
  Downloading click-8.1.7-py3-none-any.whl (97 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 97.9/97.9 KB 151.2 kB/s eta 0:00:00
Collecting marshmallow<4,>=3.18.0
  Downloading marshmallow-3.20.1-py3-none-any.whl (49 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 49.4/49.4 KB 266.0 kB/s eta 0:00:00
Collecting Flask-Babel<3,>=1
  Downloading Flask_Babel-2.0.0-py3-none-any.whl (9.3 kB)
Requirement already satisfied: setuptools>=16.0 in /usr/lib/python3/dist-packages (from opentelemetry-api==1.15.0->apache-airflow) (59.6.0)
Collecting Mako
  Downloading Mako-1.2.4-py3-none-any.whl (78 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 78.7/78.7 KB 228.4 kB/s eta 0:00:00
Collecting exceptiongroup
  Downloading exceptiongroup-1.1.3-py3-none-any.whl (14 kB)
Collecting requests<3,>=2.9.1
  Downloading requests-2.31.0-py3-none-any.whl (62 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 62.6/62.6 KB 165.0 kB/s eta 0:00:00
Collecting PyYAML<7,>=5.1
  Downloading PyYAML-6.0.1-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl (677 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 677.0/677.0 KB 213.3 kB/s eta 0:00:00
Collecting inflection<0.6,>=0.3.1
  Downloading inflection-0.5.1-py2.py3-none-any.whl (9.5 kB)
Collecting clickclick<21,>=1.2
  Downloading clickclick-20.10.2-py2.py3-none-any.whl (7.4 kB)
Collecting werkzeug>=2.0
  Downloading Werkzeug-2.2.3-py3-none-any.whl (233 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 233.6/233.6 KB 180.1 kB/s eta 0:00:00
Collecting cffi>=1.12
  Downloading cffi-1.15.1-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl (449 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 449.9/449.9 KB 229.8 kB/s eta 0:00:00
Collecting wrapt<2,>=1.10
  Downloading wrapt-1.15.0-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl (78 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 78.5/78.5 KB 244.5 kB/s eta 0:00:00
Collecting cachelib<0.10.0,>=0.9.0
  Downloading cachelib-0.9.0-py3-none-any.whl (15 kB)
Collecting jsonschema-specifications>=2023.03.6
  Downloading jsonschema_specifications-2023.7.1-py3-none-any.whl (17 kB)
Collecting referencing>=0.28.4
  Downloading referencing-0.30.2-py3-none-any.whl (25 kB)
Collecting rpds-py>=0.7.1
  Downloading rpds_py-0.9.2-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl (1.2 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 1.2/1.2 MB 217.8 kB/s eta 0:00:00
Collecting uc-micro-py
  Downloading uc_micro_py-1.0.2-py3-none-any.whl (6.2 kB)
Collecting mdurl~=0.1
  Downloading mdurl-0.1.2-py3-none-any.whl (10.0 kB)
Collecting pytzdata>=2020.1
  Downloading pytzdata-2020.1-py2.py3-none-any.whl (489 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 490.0/490.0 KB 176.4 kB/s eta 0:00:00
Collecting setuptools>=16.0
  Using cached setuptools-68.1.2-py3-none-any.whl (805 kB)
Collecting docutils
  Downloading docutils-0.20.1-py3-none-any.whl (572 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 572.7/572.7 KB 210.6 kB/s eta 0:00:00
Collecting six>=1.5
  Downloading six-1.16.0-py2.py3-none-any.whl (11 kB)
Collecting text-unidecode>=1.3
  Downloading text_unidecode-1.3-py2.py3-none-any.whl (78 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 78.2/78.2 KB 234.7 kB/s eta 0:00:00
Collecting greenlet!=0.4.17
  Downloading greenlet-2.0.2-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl (608 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 608.3/608.3 KB 223.5 kB/s eta 0:00:00
Collecting sqlparse>=0.4.2
  Downloading sqlparse-0.4.4-py3-none-any.whl (41 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 41.2/41.2 KB 197.3 kB/s eta 0:00:00
Collecting requests-toolbelt
  Downloading requests_toolbelt-1.0.0-py2.py3-none-any.whl (54 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 54.5/54.5 KB 312.7 kB/s eta 0:00:00
Collecting aiohttp
  Downloading aiohttp-3.8.5-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl (1.0 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 1.0/1.0 MB 212.9 kB/s eta 0:00:00
Collecting sniffio
  Downloading sniffio-1.3.0-py3-none-any.whl (10 kB)
Collecting httpcore<0.18.0,>=0.15.0
  Downloading httpcore-0.17.3-py3-none-any.whl (74 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 74.5/74.5 KB 145.9 kB/s eta 0:00:00
Collecting idna
  Downloading idna-3.4-py3-none-any.whl (61 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 61.5/61.5 KB 306.7 kB/s eta 0:00:00
Collecting certifi
  Downloading certifi-2023.7.22-py3-none-any.whl (158 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 158.3/158.3 KB 236.4 kB/s eta 0:00:00
Collecting opentelemetry-exporter-otlp-proto-grpc==1.19.0
  Downloading opentelemetry_exporter_otlp_proto_grpc-1.19.0-py3-none-any.whl (18 kB)
Collecting opentelemetry-exporter-otlp-proto-http==1.19.0
  Downloading opentelemetry_exporter_otlp_proto_http-1.19.0-py3-none-any.whl (17 kB)
Collecting backoff<3.0.0,>=1.10.0
  Downloading backoff-2.2.1-py3-none-any.whl (15 kB)
Collecting opentelemetry-sdk~=1.19.0
  Downloading opentelemetry_sdk-1.19.0-py3-none-any.whl (103 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 103.9/103.9 KB 269.5 kB/s eta 0:00:00
Collecting opentelemetry-exporter-otlp-proto-common==1.19.0
  Downloading opentelemetry_exporter_otlp_proto_common-1.19.0-py3-none-any.whl (17 kB)
Collecting opentelemetry-proto==1.19.0
  Downloading opentelemetry_proto-1.19.0-py3-none-any.whl (50 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 50.8/50.8 KB 123.8 kB/s eta 0:00:00
Collecting grpcio<2.0.0,>=1.0.0
  Downloading grpcio-1.57.0-cp310-cp310-manylinux_2_17_aarch64.whl (4.8 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 4.8/4.8 MB 200.8 kB/s eta 0:00:00
Collecting googleapis-common-protos~=1.52
  Downloading googleapis_common_protos-1.60.0-py2.py3-none-any.whl (227 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 227.6/227.6 KB 230.6 kB/s eta 0:00:00
Collecting protobuf<5.0,>=3.19
  Downloading protobuf-4.24.1-cp37-abi3-manylinux2014_aarch64.whl (310 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 310.4/310.4 KB 183.5 kB/s eta 0:00:00
Collecting pycparser
  Downloading pycparser-2.21-py2.py3-none-any.whl (118 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 118.7/118.7 KB 375.4 kB/s eta 0:00:00
Collecting dnspython>=1.15.0
  Downloading dnspython-2.4.2-py3-none-any.whl (300 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 300.4/300.4 KB 273.7 kB/s eta 0:00:00
Collecting Babel>=2.3
  Downloading Babel-2.12.1-py3-none-any.whl (10.1 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 10.1/10.1 MB 216.9 kB/s eta 0:00:00
Collecting pytz
  Downloading pytz-2023.3-py2.py3-none-any.whl (502 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 502.3/502.3 KB 251.7 kB/s eta 0:00:00
Collecting limits>=2.8
  Downloading limits-3.5.0-py3-none-any.whl (43 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 43.0/43.0 KB 228.5 kB/s eta 0:00:00
Collecting ordered-set<5,>4
  Downloading ordered_set-4.1.0-py3-none-any.whl (7.6 kB)
Collecting anyio<5.0,>=3.0
  Downloading anyio-3.7.1-py3-none-any.whl (80 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 80.9/80.9 KB 216.3 kB/s eta 0:00:00
Collecting h11<0.15,>=0.13
  Downloading h11-0.14.0-py3-none-any.whl (58 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 58.3/58.3 KB 306.5 kB/s eta 0:00:00
Collecting urllib3<3,>=1.21.1
  Downloading urllib3-2.0.4-py3-none-any.whl (123 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 123.9/123.9 KB 284.3 kB/s eta 0:00:00
Collecting charset-normalizer<4,>=2
  Downloading charset_normalizer-3.2.0-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl (197 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 197.9/197.9 KB 46.6 kB/s eta 0:00:00
Collecting multidict<7.0,>=4.5
  Downloading multidict-6.0.4-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl (116 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 116.6/116.6 KB 169.7 kB/s eta 0:00:00
Collecting async-timeout<5.0,>=4.0.0a3
  Downloading async_timeout-4.0.3-py3-none-any.whl (5.7 kB)
Collecting aiosignal>=1.1.2
  Downloading aiosignal-1.3.1-py3-none-any.whl (7.6 kB)
Collecting yarl<2.0,>=1.0
  Downloading yarl-1.9.2-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl (262 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 262.1/262.1 KB 168.9 kB/s eta 0:00:00
Collecting frozenlist>=1.1.1
  Downloading frozenlist-1.4.0-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl (226 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 226.5/226.5 KB 317.8 kB/s eta 0:00:00
Collecting importlib-resources>=1.3
  Downloading importlib_resources-6.0.1-py3-none-any.whl (34 kB)
INFO: pip is looking at multiple versions of multidict to determine which version is compatible with other requirements. This could take a while.
Collecting multidict<7.0,>=4.5
  Downloading multidict-6.0.3-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl (116 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 116.6/116.6 KB 280.2 kB/s eta 0:00:00
INFO: pip is looking at multiple versions of limits to determine which version is compatible with other requirements. This could take a while.
Collecting limits>=2.8
  Downloading limits-3.4.0-py3-none-any.whl (43 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 43.1/43.1 KB 205.3 kB/s eta 0:00:00
INFO: pip is looking at multiple versions of h11 to determine which version is compatible with other requirements. This could take a while.
Collecting h11<0.15,>=0.13
  Downloading h11-0.13.0-py3-none-any.whl (58 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 58.2/58.2 KB 193.8 kB/s eta 0:00:00
INFO: pip is looking at multiple versions of grpcio to determine which version is compatible with other requirements. This could take a while.
Collecting grpcio<2.0.0,>=1.0.0
  Downloading grpcio-1.56.2-cp310-cp310-manylinux_2_17_aarch64.whl (4.7 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 4.7/4.7 MB 222.2 kB/s eta 0:00:00
INFO: pip is looking at multiple versions of googleapis-common-protos to determine which version is compatible with other requirements. This could take a while.
Collecting googleapis-common-protos~=1.52
  Downloading googleapis_common_protos-1.59.1-py2.py3-none-any.whl (224 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 224.5/224.5 KB 241.0 kB/s eta 0:00:00
INFO: pip is looking at multiple versions of frozenlist to determine which version is compatible with other requirements. This could take a while.
Collecting frozenlist>=1.1.1
  Downloading frozenlist-1.3.3-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl (148 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 148.1/148.1 KB 272.3 kB/s eta 0:00:00
INFO: pip is looking at multiple versions of dnspython to determine which version is compatible with other requirements. This could take a while.
Collecting dnspython>=1.15.0
  Downloading dnspython-2.4.1-py3-none-any.whl (300 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 300.3/300.3 KB 166.2 kB/s eta 0:00:00
INFO: pip is looking at multiple versions of charset-normalizer to determine which version is compatible with other requirements. This could take a while.
Collecting charset-normalizer<4,>=2
  Downloading charset_normalizer-3.1.0-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl (195 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 195.9/195.9 KB 209.0 kB/s eta 0:00:00
INFO: pip is looking at multiple versions of backoff to determine which version is compatible with other requirements. This could take a while.
Collecting backoff<3.0.0,>=1.10.0
  Downloading backoff-2.2.0-py3-none-any.whl (15 kB)
INFO: pip is looking at multiple versions of babel to determine which version is compatible with other requirements. This could take a while.
Collecting Babel>=2.3
  Downloading Babel-2.12.0-py3-none-any.whl (10.1 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 10.1/10.1 MB 211.7 kB/s eta 0:00:00
INFO: pip is looking at multiple versions of async-timeout to determine which version is compatible with other requirements. This could take a while.
Collecting async-timeout<5.0,>=4.0.0a3
  Downloading async_timeout-4.0.2-py3-none-any.whl (5.8 kB)
INFO: pip is looking at multiple versions of anyio to determine which version is compatible with other requirements. This could take a while.
Collecting anyio<5.0,>=3.0
  Downloading anyio-3.7.0-py3-none-any.whl (80 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 80.9/80.9 KB 228.2 kB/s eta 0:00:00
INFO: pip is looking at multiple versions of aiosignal to determine which version is compatible with other requirements. This could take a while.
Collecting aiosignal>=1.1.2
  Downloading aiosignal-1.2.0-py3-none-any.whl (8.2 kB)
INFO: pip is looking at multiple versions of uc-micro-py to determine which version is compatible with other requirements. This could take a while.
Collecting uc-micro-py
  Downloading uc_micro_py-1.0.1-py3-none-any.whl (6.2 kB)
INFO: pip is looking at multiple versions of requests-toolbelt to determine which version is compatible with other requirements. This could take a while.
Collecting requests-toolbelt
  Downloading requests_toolbelt-0.10.1-py2.py3-none-any.whl (54 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 54.5/54.5 KB 223.9 kB/s eta 0:00:00
INFO: pip is looking at multiple versions of mako to determine which version is compatible with other requirements. This could take a while.
Collecting Mako
  Downloading Mako-1.2.3-py3-none-any.whl (78 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 78.7/78.7 KB 269.2 kB/s eta 0:00:00
INFO: pip is looking at multiple versions of exceptiongroup to determine which version is compatible with other requirements. This could take a while.
Collecting exceptiongroup
  Downloading exceptiongroup-1.1.2-py3-none-any.whl (14 kB)
INFO: pip is looking at multiple versions of docutils to determine which version is compatible with other requirements. This could take a while.
Collecting docutils
  Downloading docutils-0.20-py3-none-any.whl (577 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 577.9/577.9 KB 204.0 kB/s eta 0:00:00
INFO: pip is looking at multiple versions of connexion to determine which version is compatible with other requirements. This could take a while.
INFO: pip is looking at multiple versions of aiohttp to determine which version is compatible with other requirements. This could take a while.
Collecting aiohttp
  Downloading aiohttp-3.8.4-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl (1.0 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 1.0/1.0 MB 226.9 kB/s eta 0:00:00
INFO: pip is looking at multiple versions of wtforms to determine which version is compatible with other requirements. This could take a while.
Collecting WTForms<4
  Downloading WTForms-3.0.0-py3-none-any.whl (136 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 136.3/136.3 KB 194.9 kB/s eta 0:00:00
INFO: pip is looking at multiple versions of wrapt to determine which version is compatible with other requirements. This could take a while.
Collecting wrapt<2,>=1.10
  Downloading wrapt-1.14.1-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl (78 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 78.0/78.0 KB 181.4 kB/s eta 0:00:00
INFO: pip is looking at multiple versions of text-unidecode to determine which version is compatible with other requirements. This could take a while.
INFO: pip is looking at multiple versions of sqlparse to determine which version is compatible with other requirements. This could take a while.
Collecting sqlparse>=0.4.2
  Downloading sqlparse-0.4.3-py3-none-any.whl (42 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 42.8/42.8 KB 167.3 kB/s eta 0:00:00
INFO: pip is looking at multiple versions of sqlalchemy-utils to determine which version is compatible with other requirements. This could take a while.
Collecting sqlalchemy-utils<1,>=0.32.21
  Downloading SQLAlchemy_Utils-0.41.0-py3-none-any.whl (92 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 92.5/92.5 KB 277.6 kB/s eta 0:00:00
INFO: pip is looking at multiple versions of six to determine which version is compatible with other requirements. This could take a while.
Collecting six>=1.5
  Downloading six-1.15.0-py2.py3-none-any.whl (10 kB)
INFO: pip is looking at multiple versions of rpds-py to determine which version is compatible with other requirements. This could take a while.
Collecting rpds-py>=0.7.1
  Downloading rpds_py-0.8.12-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl (1.2 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 1.2/1.2 MB 200.9 kB/s eta 0:00:00
INFO: pip is looking at multiple versions of certifi to determine which version is compatible with other requirements. This could take a while.
Collecting certifi
  Downloading certifi-2023.5.7-py3-none-any.whl (156 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 157.0/157.0 KB 232.2 kB/s eta 0:00:00
INFO: pip is looking at multiple versions of requests to determine which version is compatible with other requirements. This could take a while.
Collecting requests<3,>=2.9.1
  Downloading requests-2.30.0-py3-none-any.whl (62 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 62.5/62.5 KB 212.1 kB/s eta 0:00:00
INFO: pip is looking at multiple versions of referencing to determine which version is compatible with other requirements. This could take a while.
Collecting referencing>=0.28.4
  Downloading referencing-0.30.1-py3-none-any.whl (25 kB)
INFO: pip is looking at multiple versions of pyyaml to determine which version is compatible with other requirements. This could take a while.
Collecting PyYAML<7,>=5.1
  Downloading PyYAML-6.0-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl (733 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 733.7/733.7 KB 167.1 kB/s eta 0:00:00
INFO: pip is looking at multiple versions of pytzdata to determine which version is compatible with other requirements. This could take a while.
INFO: pip is looking at multiple versions of prison to determine which version is compatible with other requirements. This could take a while.
INFO: pip is looking at multiple versions of mdurl to determine which version is compatible with other requirements. This could take a while.
Collecting mdurl~=0.1
  Downloading mdurl-0.1.1-py3-none-any.whl (10 kB)
INFO: pip is looking at multiple versions of marshmallow-sqlalchemy to determine which version is compatible with other requirements. This could take a while.
Collecting marshmallow-sqlalchemy<0.27.0,>=0.22.0
  Downloading marshmallow_sqlalchemy-0.26.0-py2.py3-none-any.whl (15 kB)
INFO: pip is looking at multiple versions of marshmallow to determine which version is compatible with other requirements. This could take a while.
Collecting marshmallow<4,>=3.18.0
  Downloading marshmallow-3.20.0-py3-none-any.whl (49 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 49.4/49.4 KB 278.4 kB/s eta 0:00:00
INFO: pip is looking at multiple versions of jsonschema-specifications to determine which version is compatible with other requirements. This could take a while.
Collecting jsonschema-specifications>=2023.03.6
  Downloading jsonschema_specifications-2023.6.1-py3-none-any.whl (17 kB)
INFO: pip is looking at multiple versions of inflection to determine which version is compatible with other requirements. This could take a while.
Collecting inflection<0.6,>=0.3.1
  Downloading inflection-0.5.0-py2.py3-none-any.whl (5.8 kB)
INFO: pip is looking at multiple versions of idna to determine which version is compatible with other requirements. This could take a while.
Collecting idna
  Downloading idna-3.3-py3-none-any.whl (61 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 61.2/61.2 KB 121.2 kB/s eta 0:00:00
INFO: pip is looking at multiple versions of sniffio to determine which version is compatible with other requirements. This could take a while.
Collecting sniffio
  Downloading sniffio-1.2.0-py3-none-any.whl (10 kB)
  Downloading sniffio-1.1.0-py3-none-any.whl (4.5 kB)
  Downloading sniffio-1.0.0-py3-none-any.whl (4.4 kB)
INFO: pip is looking at multiple versions of httpcore to determine which version is compatible with other requirements. This could take a while.
Collecting httpcore<0.18.0,>=0.15.0
  Downloading httpcore-0.17.2-py3-none-any.whl (72 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 72.5/72.5 KB 184.4 kB/s eta 0:00:00
INFO: pip is looking at multiple versions of greenlet to determine which version is compatible with other requirements. This could take a while.
Collecting greenlet!=0.4.17
  Downloading greenlet-2.0.1-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl (529 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 529.6/529.6 KB 193.8 kB/s eta 0:00:00
INFO: pip is looking at multiple versions of flask-sqlalchemy to determine which version is compatible with other requirements. This could take a while.
Collecting Flask-SQLAlchemy<3,>=2.4
  Downloading Flask_SQLAlchemy-2.5.0-py2.py3-none-any.whl (17 kB)
INFO: pip is looking at multiple versions of flask-limiter to determine which version is compatible with other requirements. This could take a while.
Collecting Flask-Limiter<4,>3
  Downloading Flask_Limiter-3.3.1-py3-none-any.whl (27 kB)
INFO: pip is looking at multiple versions of flask-jwt-extended to determine which version is compatible with other requirements. This could take a while.
Collecting Flask-JWT-Extended<5.0.0,>=4.0.0
  Downloading Flask_JWT_Extended-4.5.1-py2.py3-none-any.whl (22 kB)
INFO: pip is looking at multiple versions of flask-babel to determine which version is compatible with other requirements. This could take a while.
Collecting Flask-Babel<3,>=1
  Downloading Flask_Babel-1.0.0-py3-none-any.whl (9.5 kB)
INFO: pip is looking at multiple versions of email-validator to determine which version is compatible with other requirements. This could take a while.
Collecting email-validator<2,>=1.0.5
  Downloading email_validator-1.3.0-py2.py3-none-any.whl (22 kB)
INFO: pip is looking at multiple versions of colorama to determine which version is compatible with other requirements. This could take a while.
Collecting colorama<1,>=0.3.9
  Downloading colorama-0.4.5-py2.py3-none-any.whl (16 kB)
INFO: pip is looking at multiple versions of clickclick to determine which version is compatible with other requirements. This could take a while.
Collecting clickclick<21,>=1.2
  Downloading clickclick-20.10.1-py2.py3-none-any.whl (7.4 kB)
INFO: pip is looking at multiple versions of click to determine which version is compatible with other requirements. This could take a while.
Collecting click<9,>=8
  Downloading click-8.1.6-py3-none-any.whl (97 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 97.9/97.9 KB 288.0 kB/s eta 0:00:00
INFO: pip is looking at multiple versions of cffi to determine which version is compatible with other requirements. This could take a while.
Collecting cffi>=1.12
  Downloading cffi-1.15.0-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl (448 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 448.3/448.3 KB 197.3 kB/s eta 0:00:00
INFO: pip is looking at multiple versions of cachelib to determine which version is compatible with other requirements. This could take a while.
INFO: pip is looking at multiple versions of apispec[yaml] to determine which version is compatible with other requirements. This could take a while.
Collecting apispec[yaml]<7,>=6.0.0
  Downloading apispec-6.2.0-py3-none-any.whl (29 kB)
INFO: pip is looking at multiple versions of opentelemetry-proto to determine which version is compatible with other requirements. This could take a while.
INFO: pip is looking at multiple versions of opentelemetry-exporter-otlp-proto-common to determine which version is compatible with other requirements. This could take a while.
INFO: pip is looking at multiple versions of opentelemetry-exporter-otlp-proto-http to determine which version is compatible with other requirements. This could take a while.
INFO: pip is looking at multiple versions of opentelemetry-exporter-otlp-proto-grpc to determine which version is compatible with other requirements. This could take a while.
INFO: pip is looking at multiple versions of opentelemetry-exporter-otlp to determine which version is compatible with other requirements. This could take a while.
Collecting opentelemetry-exporter-otlp
  Downloading opentelemetry_exporter_otlp-1.18.0-py3-none-any.whl (7.0 kB)
Collecting opentelemetry-exporter-otlp-proto-grpc==1.18.0
  Downloading opentelemetry_exporter_otlp_proto_grpc-1.18.0-py3-none-any.whl (18 kB)
Collecting opentelemetry-exporter-otlp-proto-http==1.18.0
  Downloading opentelemetry_exporter_otlp_proto_http-1.18.0-py3-none-any.whl (17 kB)
Collecting opentelemetry-exporter-otlp-proto-common==1.18.0
  Downloading opentelemetry_exporter_otlp_proto_common-1.18.0-py3-none-any.whl (17 kB)
Collecting opentelemetry-proto==1.18.0
  Downloading opentelemetry_proto-1.18.0-py3-none-any.whl (52 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 52.6/52.6 KB 231.1 kB/s eta 0:00:00
Collecting opentelemetry-sdk~=1.18.0
  Downloading opentelemetry_sdk-1.18.0-py3-none-any.whl (101 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 101.6/101.6 KB 142.6 kB/s eta 0:00:00
Collecting opentelemetry-semantic-conventions==0.39b0
  Downloading opentelemetry_semantic_conventions-0.39b0-py3-none-any.whl (26 kB)
Collecting opentelemetry-exporter-otlp
  Downloading opentelemetry_exporter_otlp-1.17.0-py3-none-any.whl (7.0 kB)
Collecting opentelemetry-exporter-otlp-proto-http==1.17.0
  Downloading opentelemetry_exporter_otlp_proto_http-1.17.0-py3-none-any.whl (21 kB)
Collecting opentelemetry-exporter-otlp-proto-grpc==1.17.0
  Downloading opentelemetry_exporter_otlp_proto_grpc-1.17.0-py3-none-any.whl (21 kB)
Collecting opentelemetry-proto==1.17.0
  Downloading opentelemetry_proto-1.17.0-py3-none-any.whl (52 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 52.6/52.6 KB 245.5 kB/s eta 0:00:00
Collecting opentelemetry-sdk~=1.17.0
  Downloading opentelemetry_sdk-1.17.0-py3-none-any.whl (100 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 100.0/100.0 KB 229.6 kB/s eta 0:00:00
Collecting opentelemetry-exporter-otlp
  Downloading opentelemetry_exporter_otlp-1.16.0-py3-none-any.whl (7.0 kB)
Collecting opentelemetry-exporter-otlp-proto-grpc==1.16.0
  Downloading opentelemetry_exporter_otlp_proto_grpc-1.16.0-py3-none-any.whl (20 kB)
Collecting opentelemetry-exporter-otlp-proto-http==1.16.0
  Downloading opentelemetry_exporter_otlp_proto_http-1.16.0-py3-none-any.whl (21 kB)
Collecting opentelemetry-proto==1.16.0
  Downloading opentelemetry_proto-1.16.0-py3-none-any.whl (52 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 52.6/52.6 KB 211.8 kB/s eta 0:00:00
Collecting opentelemetry-sdk~=1.16.0
  Downloading opentelemetry_sdk-1.16.0-py3-none-any.whl (94 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 94.6/94.6 KB 214.6 kB/s eta 0:00:00
Collecting opentelemetry-semantic-conventions==0.37b0
  Downloading opentelemetry_semantic_conventions-0.37b0-py3-none-any.whl (26 kB)
Collecting opentelemetry-exporter-otlp
  Downloading opentelemetry_exporter_otlp-1.15.0-py3-none-any.whl (7.0 kB)
Collecting opentelemetry-exporter-otlp-proto-grpc==1.15.0
  Downloading opentelemetry_exporter_otlp_proto_grpc-1.15.0-py3-none-any.whl (20 kB)
Collecting opentelemetry-exporter-otlp-proto-http==1.15.0
  Downloading opentelemetry_exporter_otlp_proto_http-1.15.0-py3-none-any.whl (21 kB)
Collecting opentelemetry-proto==1.15.0
  Downloading opentelemetry_proto-1.15.0-py3-none-any.whl (52 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 52.6/52.6 KB 218.4 kB/s eta 0:00:00
Collecting opentelemetry-sdk~=1.12
  Downloading opentelemetry_sdk-1.15.0-py3-none-any.whl (94 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 94.5/94.5 KB 134.8 kB/s eta 0:00:00
Collecting opentelemetry-semantic-conventions==0.36b0
  Downloading opentelemetry_semantic_conventions-0.36b0-py3-none-any.whl (26 kB)
Building wheels for collected packages: cron-descriptor, pendulum, psutil, python-nvd3, unicodecsv
  Building wheel for cron-descriptor (setup.py) ... done
  Created wheel for cron-descriptor: filename=cron_descriptor-1.4.0-py3-none-any.whl size=49856 sha256=0d3d94f0635d798ea595674331de8cb95be28be8ff237120e65a36b5a51b88a5
  Stored in directory: /root/.cache/pip/wheels/98/ff/fb/d908f229155ad6b65c7a34e9d35774fd1f40579241c3a5f924
  Building wheel for pendulum (pyproject.toml) ... done
  Created wheel for pendulum: filename=pendulum-2.1.2-cp310-cp310-manylinux_2_35_aarch64.whl size=158015 sha256=af65514e9237e8967436953db842dc8f145682f5377b588178d926e0bbc4c84f
  Stored in directory: /root/.cache/pip/wheels/2e/41/ed/f113e4c9dc10f6c846d69f412e9cd9aa429960a3e2e485a4f9
  Building wheel for psutil (pyproject.toml) ... done
  Created wheel for psutil: filename=psutil-5.9.5-cp310-abi3-linux_aarch64.whl size=281049 sha256=24b9d53e86c863b06a1a53f683f61687a65950ad89abcd87b09dd99d870eb8bb
  Stored in directory: /root/.cache/pip/wheels/1f/3a/db/ba9717f3efd7f8da8910eca12dc9cd15d404035397af627e7c
  Building wheel for python-nvd3 (setup.py) ... done
  Created wheel for python-nvd3: filename=python_nvd3-0.15.0-py3-none-any.whl size=38167 sha256=dcd64837d052bf2cb74bf2bb1ff63aa18b1ba51f29990074bfb2bca0272d2fe0
  Stored in directory: /root/.cache/pip/wheels/80/e7/4e/d99e473adde7dd21b9938d4d32bf823ca334e7979632d6a64c
  Building wheel for unicodecsv (setup.py) ... done
  Created wheel for unicodecsv: filename=unicodecsv-0.14.1-py3-none-any.whl size=10768 sha256=39041c66a083365849adb9f4bb406a0cace02f3ce06117ad63ba0be4a89d95e8
  Stored in directory: /root/.cache/pip/wheels/9c/ea/66/8e45247b09052a933eb1a680b7c64802298faba58aac9b346b
Successfully built cron-descriptor pendulum psutil python-nvd3 unicodecsv
Installing collected packages: unicodecsv, text-unidecode, pytz, lockfile, cron-descriptor, colorlog, wrapt, urllib3, uc-micro-py, typing-extensions, termcolor, tenacity, tabulate, sqlparse, sniffio, six, setuptools, setproctitle, rpds-py, PyYAML, pytzdata, python-slugify, pyjwt, pygments, pycparser, psutil, protobuf, pluggy, pathspec, packaging, ordered-set, opentelemetry-semantic-conventions, multidict, mdurl, markupsafe, markdown, lazy-object-proxy, itsdangerous, inflection, importlib-resources, idna, h11, grpcio, greenlet, graphviz, google-re2, frozenlist, exceptiongroup, docutils, dnspython, dill, configupdater, colorama, click, charset-normalizer, certifi, cachelib, blinker, backoff, Babel, attrs, async-timeout, argcomplete, yarl, WTForms, werkzeug, sqlalchemy, rfc3339-validator, requests, referencing, python-dateutil, python-daemon, pydantic, prison, opentelemetry-proto, marshmallow, markdown-it-py, Mako, linkify-it-py, jinja2, gunicorn, googleapis-common-protos, email-validator, deprecated, clickclick, cffi, cattrs, asgiref, apispec, anyio, aiosignal, sqlalchemy-utils, sqlalchemy-jsonfield, rich, requests-toolbelt, python-nvd3, pendulum, opentelemetry-api, mdit-py-plugins, marshmallow-sqlalchemy, marshmallow-oneofschema, limits, jsonschema-specifications, httpcore, flask, cryptography, croniter, alembic, aiohttp, rich-argparse, opentelemetry-sdk, jsonschema, httpx, flask-wtf, Flask-SQLAlchemy, flask-session, flask-login, Flask-Limiter, Flask-JWT-Extended, flask-caching, Flask-Babel, opentelemetry-exporter-otlp-proto-http, opentelemetry-exporter-otlp-proto-grpc, flask-appbuilder, connexion, opentelemetry-exporter-otlp, apache-airflow-providers-common-sql, apache-airflow-providers-sqlite, apache-airflow-providers-imap, apache-airflow-providers-http, apache-airflow-providers-ftp, apache-airflow
  Attempting uninstall: setuptools
    Found existing installation: setuptools 59.6.0
    Not uninstalling setuptools at /usr/lib/python3/dist-packages, outside environment /usr
    Can't uninstall 'setuptools'. No files were found to uninstall.
Successfully installed Babel-2.12.1 Flask-Babel-2.0.0 Flask-JWT-Extended-4.5.2 Flask-Limiter-3.4.0 Flask-SQLAlchemy-2.5.1 Mako-1.2.4 PyYAML-6.0.1 WTForms-3.0.1 aiohttp-3.8.5 aiosignal-1.3.1 alembic-1.11.3 anyio-3.7.1 apache-airflow-2.7.0 apache-airflow-providers-common-sql-1.7.0 apache-airflow-providers-ftp-3.5.0 apache-airflow-providers-http-4.5.0 apache-airflow-providers-imap-3.3.0 apache-airflow-providers-sqlite-3.4.3 apispec-6.3.0 argcomplete-3.1.1 asgiref-3.7.2 async-timeout-4.0.3 attrs-23.1.0 backoff-2.2.1 blinker-1.6.2 cachelib-0.9.0 cattrs-23.1.2 certifi-2023.7.22 cffi-1.15.1 charset-normalizer-3.2.0 click-8.1.7 clickclick-20.10.2 colorama-0.4.6 colorlog-4.8.0 configupdater-3.1.1 connexion-2.14.2 cron-descriptor-1.4.0 croniter-1.4.1 cryptography-41.0.3 deprecated-1.2.14 dill-0.3.7 dnspython-2.4.2 docutils-0.20.1 email-validator-1.3.1 exceptiongroup-1.1.3 flask-2.2.5 flask-appbuilder-4.3.3 flask-caching-2.0.2 flask-login-0.6.2 flask-session-0.5.0 flask-wtf-1.1.1 frozenlist-1.4.0 google-re2-1.1 googleapis-common-protos-1.60.0 graphviz-0.20.1 greenlet-2.0.2 grpcio-1.57.0 gunicorn-21.2.0 h11-0.14.0 httpcore-0.17.3 httpx-0.24.1 idna-3.4 importlib-resources-6.0.1 inflection-0.5.1 itsdangerous-2.1.2 jinja2-3.1.2 jsonschema-4.19.0 jsonschema-specifications-2023.7.1 lazy-object-proxy-1.9.0 limits-3.5.0 linkify-it-py-2.0.2 lockfile-0.12.2 markdown-3.4.4 markdown-it-py-3.0.0 markupsafe-2.1.3 marshmallow-3.20.1 marshmallow-oneofschema-3.0.1 marshmallow-sqlalchemy-0.26.1 mdit-py-plugins-0.4.0 mdurl-0.1.2 multidict-6.0.4 opentelemetry-api-1.15.0 opentelemetry-exporter-otlp-1.15.0 opentelemetry-exporter-otlp-proto-grpc-1.15.0 opentelemetry-exporter-otlp-proto-http-1.15.0 opentelemetry-proto-1.15.0 opentelemetry-sdk-1.15.0 opentelemetry-semantic-conventions-0.36b0 ordered-set-4.1.0 packaging-23.1 pathspec-0.11.2 pendulum-2.1.2 pluggy-1.2.0 prison-0.2.1 protobuf-4.24.1 psutil-5.9.5 pycparser-2.21 pydantic-1.10.12 pygments-2.16.1 pyjwt-2.8.0 python-daemon-3.0.1 python-dateutil-2.8.2 python-nvd3-0.15.0 python-slugify-8.0.1 pytz-2023.3 pytzdata-2020.1 referencing-0.30.2 requests-2.31.0 requests-toolbelt-1.0.0 rfc3339-validator-0.1.4 rich-13.5.2 rich-argparse-1.3.0 rpds-py-0.9.2 setproctitle-1.3.2 setuptools-68.1.2 six-1.16.0 sniffio-1.3.0 sqlalchemy-1.4.49 sqlalchemy-jsonfield-1.0.1.post0 sqlalchemy-utils-0.41.1 sqlparse-0.4.4 tabulate-0.9.0 tenacity-8.2.3 termcolor-2.3.0 text-unidecode-1.3 typing-extensions-4.7.1 uc-micro-py-1.0.2 unicodecsv-0.14.1 urllib3-2.0.4 werkzeug-2.2.3 wrapt-1.15.0 yarl-1.9.2
WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# airflow db init
/usr/local/lib/python3.10/dist-packages/airflow/cli/commands/db_command.py:43 DeprecationWarning: `db init` is deprecated.  Use `db migrate` instead to migrate the db and/or airflow connections create-default-connections to create the default connections
DB: sqlite:////root/airflow/airflow.db
[2023-08-23T19:08:06.291+0000] {migration.py:213} INFO - Context impl SQLiteImpl.
[2023-08-23T19:08:06.291+0000] {migration.py:216} INFO - Will assume non-transactional DDL.
INFO  [alembic.runtime.migration] Context impl SQLiteImpl.
INFO  [alembic.runtime.migration] Will assume non-transactional DDL.
INFO  [alembic.runtime.migration] Running stamp_revision  -> 405de8318b3a
WARNI [airflow.models.crypto] empty cryptography key - values will not be stored encrypted.
Initialization done
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# 
root@2a2814f91f18:/# cd /root/airflow/ 
root@2a2814f91f18:~/airflow# ls
airflow.cfg  airflow.db  logs
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# apt-get install nano
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
Suggested packages:
  hunspell
The following NEW packages will be installed:
  nano
0 upgraded, 1 newly installed, 0 to remove and 2 not upgraded.
Need to get 277 kB of archives.
After this operation, 872 kB of additional disk space will be used.
Get:1 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 nano arm64 6.2-1 [277 kB]
Fetched 277 kB in 11s (24.3 kB/s)
debconf: delaying package configuration, since apt-utils is not installed
Selecting previously unselected package nano.
(Reading database ... 16143 files and directories currently installed.)
Preparing to unpack .../archives/nano_6.2-1_arm64.deb ...
Unpacking nano (6.2-1) ...
Setting up nano (6.2-1) ...
update-alternatives: using /bin/nano to provide /usr/bin/editor (editor) in auto mode
update-alternatives: warning: skip creation of /usr/share/man/man1/editor.1.gz because associated file /usr/share/man/man1/nano.1.gz (of link group editor) doesn't exist
update-alternatives: using /bin/nano to provide /usr/bin/pico (pico) in auto mode
update-alternatives: warning: skip creation of /usr/share/man/man1/pico.1.gz because associated file /usr/share/man/man1/nano.1.gz (of link group pico) doesn't exist
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# nano airflow.cfg
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# airflow db init
/usr/local/lib/python3.10/dist-packages/airflow/configuration.py:799 FutureWarning: Bad scheme in Airflow configuration core > sql_alchemy_conn: `postgres`. As of SQLAlchemy 1.4 (adopted in Airflow 2.3) this is no longer supported.  You must change to `postgresql` before the next Airflow release.
[2023-08-23T19:15:12.087+0000] {cli_parser.py:56} ERROR - Failed to load CLI commands from executor: CeleryExecutor
Traceback (most recent call last):
  File "/usr/local/lib/python3.10/dist-packages/airflow/cli/cli_parser.py", line 52, in <module>
    executor, _ = ExecutorLoader.import_default_executor_cls(validate=False)
  File "/usr/local/lib/python3.10/dist-packages/airflow/executors/executor_loader.py", line 169, in import_default_executor_cls
    executor, source = cls.import_executor_cls(executor_name, validate=validate)
  File "/usr/local/lib/python3.10/dist-packages/airflow/executors/executor_loader.py", line 143, in import_executor_cls
    return _import_and_validate(cls.executors[executor_name]), ConnectorSource.CORE
  File "/usr/local/lib/python3.10/dist-packages/airflow/executors/executor_loader.py", line 137, in _import_and_validate
    executor = import_string(path)
  File "/usr/local/lib/python3.10/dist-packages/airflow/utils/module_loading.py", line 37, in import_string
    module = import_module(module_path)
  File "/usr/lib/python3.10/importlib/__init__.py", line 126, in import_module
    return _bootstrap._gcd_import(name[level:], package, level)
  File "<frozen importlib._bootstrap>", line 1050, in _gcd_import
  File "<frozen importlib._bootstrap>", line 1027, in _find_and_load
  File "<frozen importlib._bootstrap>", line 992, in _find_and_load_unlocked
  File "<frozen importlib._bootstrap>", line 241, in _call_with_frames_removed
  File "<frozen importlib._bootstrap>", line 1050, in _gcd_import
  File "<frozen importlib._bootstrap>", line 1027, in _find_and_load
  File "<frozen importlib._bootstrap>", line 992, in _find_and_load_unlocked
  File "<frozen importlib._bootstrap>", line 241, in _call_with_frames_removed
  File "<frozen importlib._bootstrap>", line 1050, in _gcd_import
  File "<frozen importlib._bootstrap>", line 1027, in _find_and_load
  File "<frozen importlib._bootstrap>", line 1004, in _find_and_load_unlocked
ModuleNotFoundError: No module named 'airflow.providers.celery'
[2023-08-23T19:15:12.088+0000] {cli_parser.py:57} ERROR - Ensure all dependencies are met and try again. If using a Celery based executor install a 3.3.0+ version of the Celery provider. If using a Kubernetes executor, install a 7.4.0+ version of the CNCF provider
/usr/local/lib/python3.10/dist-packages/airflow/cli/commands/db_command.py:43 DeprecationWarning: `db init` is deprecated.  Use `db migrate` instead to migrate the db and/or airflow connections create-default-connections to create the default connections
DB: postgresql://postgres:***@172.17.0.3:5432/postgres
[2023-08-23T19:15:12.292+0000] {migration.py:213} INFO - Context impl PostgresqlImpl.
[2023-08-23T19:15:12.292+0000] {migration.py:216} INFO - Will assume transactional DDL.
[2023-08-23T19:15:12.476+0000] {migration.py:213} INFO - Context impl PostgresqlImpl.
[2023-08-23T19:15:12.476+0000] {migration.py:216} INFO - Will assume transactional DDL.
[2023-08-23T19:15:12.482+0000] {db.py:1633} INFO - Creating tables
INFO  [alembic.runtime.migration] Context impl PostgresqlImpl.
INFO  [alembic.runtime.migration] Will assume transactional DDL.
WARNI [airflow.models.crypto] empty cryptography key - values will not be stored encrypted.
Initialization done
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# pip3 install celery
Collecting celery
  Downloading celery-5.3.1-py3-none-any.whl (420 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 420.4/420.4 KB 270.6 kB/s eta 0:00:00
Collecting vine<6.0,>=5.0.0
  Downloading vine-5.0.0-py2.py3-none-any.whl (9.4 kB)
Collecting click-plugins>=1.1.1
  Downloading click_plugins-1.1.1-py2.py3-none-any.whl (7.5 kB)
Collecting kombu<6.0,>=5.3.1
  Downloading kombu-5.3.1-py3-none-any.whl (198 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 198.5/198.5 KB 279.3 kB/s eta 0:00:00
Requirement already satisfied: python-dateutil>=2.8.2 in /usr/local/lib/python3.10/dist-packages (from celery) (2.8.2)
Collecting click-didyoumean>=0.3.0
  Downloading click_didyoumean-0.3.0-py3-none-any.whl (2.7 kB)
Collecting click-repl>=0.2.0
  Downloading click_repl-0.3.0-py3-none-any.whl (10 kB)
Collecting tzdata>=2022.7
  Downloading tzdata-2023.3-py2.py3-none-any.whl (341 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 341.8/341.8 KB 283.1 kB/s eta 0:00:00
Collecting billiard<5.0,>=4.1.0
  Downloading billiard-4.1.0-py3-none-any.whl (86 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 86.7/86.7 KB 213.8 kB/s eta 0:00:00
Requirement already satisfied: click<9.0,>=8.1.2 in /usr/local/lib/python3.10/dist-packages (from celery) (8.1.7)
Collecting prompt-toolkit>=3.0.36
  Downloading prompt_toolkit-3.0.39-py3-none-any.whl (385 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 385.2/385.2 KB 293.8 kB/s eta 0:00:00
Collecting amqp<6.0.0,>=5.1.1
  Downloading amqp-5.1.1-py3-none-any.whl (50 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 50.8/50.8 KB 646.6 kB/s eta 0:00:00
Requirement already satisfied: six>=1.5 in /usr/local/lib/python3.10/dist-packages (from python-dateutil>=2.8.2->celery) (1.16.0)
Collecting wcwidth
  Downloading wcwidth-0.2.6-py2.py3-none-any.whl (29 kB)
Installing collected packages: wcwidth, vine, tzdata, prompt-toolkit, click-plugins, click-didyoumean, billiard, click-repl, amqp, kombu, celery
Successfully installed amqp-5.1.1 billiard-4.1.0 celery-5.3.1 click-didyoumean-0.3.0 click-plugins-1.1.1 click-repl-0.3.0 kombu-5.3.1 prompt-toolkit-3.0.39 tzdata-2023.3 vine-5.0.0 wcwidth-0.2.6
WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# pip3 install apache-airflow-providers-sftp
Collecting apache-airflow-providers-sftp
  Downloading apache_airflow_providers_sftp-4.5.0-py3-none-any.whl (24 kB)
Collecting apache-airflow-providers-ssh>=2.1.0
  Downloading apache_airflow_providers_ssh-3.7.1-py3-none-any.whl (22 kB)
Requirement already satisfied: apache-airflow>=2.4.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow-providers-sftp) (2.7.0)
Requirement already satisfied: linkify-it-py>=2.0.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (2.0.2)
Requirement already satisfied: setproctitle>=1.1.8 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.3.2)
Requirement already satisfied: flask-wtf>=0.15 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.1.1)
Requirement already satisfied: pluggy>=1.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.2.0)
Requirement already satisfied: python-dateutil>=2.3 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (2.8.2)
Requirement already satisfied: alembic<2.0,>=1.6.3 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.11.3)
Requirement already satisfied: flask-appbuilder==4.3.3 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (4.3.3)
Requirement already satisfied: rich-argparse>=1.0.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.3.0)
Requirement already satisfied: tabulate>=0.7.5 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (0.9.0)
Requirement already satisfied: termcolor>=1.1.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (2.3.0)
Requirement already satisfied: lockfile>=0.12.2 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (0.12.2)
Requirement already satisfied: python-daemon>=3.0.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (3.0.1)
Requirement already satisfied: jinja2>=3.0.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (3.1.2)
Requirement already satisfied: apache-airflow-providers-imap in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (3.3.0)
Requirement already satisfied: opentelemetry-api==1.15.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.15.0)
Requirement already satisfied: flask-session>=0.4.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (0.5.0)
Requirement already satisfied: dill>=0.2.2 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (0.3.7)
Requirement already satisfied: graphviz>=0.12 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (0.20.1)
Requirement already satisfied: google-re2>=1.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.1)
Requirement already satisfied: sqlalchemy-jsonfield>=1.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.0.1.post0)
Requirement already satisfied: argcomplete>=1.10 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (3.1.1)
Requirement already satisfied: python-nvd3>=0.15.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (0.15.0)
Requirement already satisfied: sqlalchemy<2.0,>=1.4 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.4.49)
Requirement already satisfied: apache-airflow-providers-http in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (4.5.0)
Requirement already satisfied: opentelemetry-exporter-otlp in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.15.0)
Requirement already satisfied: cryptography>=0.9.3 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (41.0.3)
Requirement already satisfied: apache-airflow-providers-ftp in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (3.5.0)
Requirement already satisfied: pathspec>=0.9.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (0.11.2)
Requirement already satisfied: pydantic<2.0.0,>=1.10.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.10.12)
Requirement already satisfied: tenacity!=8.2.0,>=6.2.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (8.2.3)
Requirement already satisfied: pendulum>=2.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (2.1.2)
Requirement already satisfied: flask<2.3,>=2.2 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (2.2.5)
Requirement already satisfied: jsonschema>=4.18.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (4.19.0)
Requirement already satisfied: apache-airflow-providers-sqlite in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (3.4.3)
Requirement already satisfied: flask-caching>=1.5.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (2.0.2)
Requirement already satisfied: lazy-object-proxy in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.9.0)
Requirement already satisfied: markdown>=3.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (3.4.4)
Requirement already satisfied: apache-airflow-providers-common-sql in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.7.0)
Requirement already satisfied: flask-login>=0.6.2 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (0.6.2)
Requirement already satisfied: unicodecsv>=0.14.1 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (0.14.1)
Requirement already satisfied: python-slugify>=5.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (8.0.1)
Requirement already satisfied: marshmallow-oneofschema>=2.0.1 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (3.0.1)
Requirement already satisfied: pyjwt>=2.0.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (2.8.0)
Requirement already satisfied: psutil>=4.2.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (5.9.5)
Requirement already satisfied: configupdater>=3.1.1 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (3.1.1)
Requirement already satisfied: rfc3339-validator>=0.1.4 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (0.1.4)
Requirement already satisfied: pygments>=2.0.1 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (2.16.1)
Requirement already satisfied: markdown-it-py>=2.1.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (3.0.0)
Requirement already satisfied: cattrs>=22.1.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (23.1.2)
Requirement already satisfied: typing-extensions>=4.0.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (4.7.1)
Requirement already satisfied: colorlog<5.0,>=4.0.2 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (4.8.0)
Requirement already satisfied: markupsafe>=1.1.1 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (2.1.3)
Requirement already satisfied: cron-descriptor>=1.2.24 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.4.0)
Requirement already satisfied: mdit-py-plugins>=0.3.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (0.4.0)
Requirement already satisfied: connexion[flask]>=2.10.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (2.14.2)
Requirement already satisfied: gunicorn>=20.1.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (21.2.0)
Requirement already satisfied: attrs>=22.1.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (23.1.0)
Requirement already satisfied: asgiref in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (3.7.2)
Requirement already satisfied: blinker in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.6.2)
Requirement already satisfied: itsdangerous>=2.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (2.1.2)
Requirement already satisfied: deprecated>=1.2.13 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.2.14)
Requirement already satisfied: rich>=12.4.4 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (13.5.2)
Requirement already satisfied: werkzeug>=2.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (2.2.3)
Requirement already satisfied: croniter>=0.3.17 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.4.1)
Requirement already satisfied: packaging>=14.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (23.1)
Requirement already satisfied: httpx in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-sftp) (0.24.1)
Requirement already satisfied: marshmallow<4,>=3.18.0 in /usr/local/lib/python3.10/dist-packages (from flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (3.20.1)
Requirement already satisfied: Flask-JWT-Extended<5.0.0,>=4.0.0 in /usr/local/lib/python3.10/dist-packages (from flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (4.5.2)
Requirement already satisfied: colorama<1,>=0.3.9 in /usr/local/lib/python3.10/dist-packages (from flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (0.4.6)
Requirement already satisfied: Flask-Limiter<4,>3 in /usr/local/lib/python3.10/dist-packages (from flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (3.4.0)
Requirement already satisfied: Flask-SQLAlchemy<3,>=2.4 in /usr/local/lib/python3.10/dist-packages (from flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (2.5.1)
Requirement already satisfied: email-validator<2,>=1.0.5 in /usr/local/lib/python3.10/dist-packages (from flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.3.1)
Requirement already satisfied: sqlalchemy-utils<1,>=0.32.21 in /usr/local/lib/python3.10/dist-packages (from flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (0.41.1)
Requirement already satisfied: apispec[yaml]<7,>=6.0.0 in /usr/local/lib/python3.10/dist-packages (from flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (6.3.0)
Requirement already satisfied: click<9,>=8 in /usr/local/lib/python3.10/dist-packages (from flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (8.1.7)
Requirement already satisfied: WTForms<4 in /usr/local/lib/python3.10/dist-packages (from flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (3.0.1)
Requirement already satisfied: prison<1.0.0,>=0.2.1 in /usr/local/lib/python3.10/dist-packages (from flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (0.2.1)
Requirement already satisfied: marshmallow-sqlalchemy<0.27.0,>=0.22.0 in /usr/local/lib/python3.10/dist-packages (from flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (0.26.1)
Requirement already satisfied: Flask-Babel<3,>=1 in /usr/local/lib/python3.10/dist-packages (from flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (2.0.0)
Requirement already satisfied: setuptools>=16.0 in /usr/local/lib/python3.10/dist-packages (from opentelemetry-api==1.15.0->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (68.1.2)
Collecting paramiko>=2.6.0
  Downloading paramiko-3.3.1-py3-none-any.whl (224 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 224.8/224.8 KB 353.7 kB/s eta 0:00:00
Collecting sshtunnel>=0.3.2
  Downloading sshtunnel-0.4.0-py2.py3-none-any.whl (24 kB)
Requirement already satisfied: Mako in /usr/local/lib/python3.10/dist-packages (from alembic<2.0,>=1.6.3->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.2.4)
Requirement already satisfied: exceptiongroup in /usr/local/lib/python3.10/dist-packages (from cattrs>=22.1.0->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.1.3)
Requirement already satisfied: inflection<0.6,>=0.3.1 in /usr/local/lib/python3.10/dist-packages (from connexion[flask]>=2.10.0->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (0.5.1)
Requirement already satisfied: requests<3,>=2.9.1 in /usr/local/lib/python3.10/dist-packages (from connexion[flask]>=2.10.0->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (2.31.0)
Requirement already satisfied: clickclick<21,>=1.2 in /usr/local/lib/python3.10/dist-packages (from connexion[flask]>=2.10.0->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (20.10.2)
Requirement already satisfied: PyYAML<7,>=5.1 in /usr/local/lib/python3.10/dist-packages (from connexion[flask]>=2.10.0->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (6.0.1)
Requirement already satisfied: cffi>=1.12 in /usr/local/lib/python3.10/dist-packages (from cryptography>=0.9.3->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.15.1)
Requirement already satisfied: wrapt<2,>=1.10 in /usr/local/lib/python3.10/dist-packages (from deprecated>=1.2.13->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.15.0)
Requirement already satisfied: cachelib<0.10.0,>=0.9.0 in /usr/local/lib/python3.10/dist-packages (from flask-caching>=1.5.0->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (0.9.0)
Requirement already satisfied: rpds-py>=0.7.1 in /usr/local/lib/python3.10/dist-packages (from jsonschema>=4.18.0->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (0.9.2)
Requirement already satisfied: jsonschema-specifications>=2023.03.6 in /usr/local/lib/python3.10/dist-packages (from jsonschema>=4.18.0->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (2023.7.1)
Requirement already satisfied: referencing>=0.28.4 in /usr/local/lib/python3.10/dist-packages (from jsonschema>=4.18.0->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (0.30.2)
Requirement already satisfied: uc-micro-py in /usr/local/lib/python3.10/dist-packages (from linkify-it-py>=2.0.0->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.0.2)
Requirement already satisfied: mdurl~=0.1 in /usr/local/lib/python3.10/dist-packages (from markdown-it-py>=2.1.0->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (0.1.2)
Collecting pynacl>=1.5
  Downloading PyNaCl-1.5.0-cp36-abi3-manylinux_2_17_aarch64.manylinux2014_aarch64.manylinux_2_24_aarch64.whl (601 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 601.7/601.7 KB 222.5 kB/s eta 0:00:00
Collecting bcrypt>=3.2
  Downloading bcrypt-4.0.1-cp36-abi3-manylinux_2_28_aarch64.whl (583 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 583.6/583.6 KB 257.8 kB/s eta 0:00:00
Requirement already satisfied: pytzdata>=2020.1 in /usr/local/lib/python3.10/dist-packages (from pendulum>=2.0->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (2020.1)
Requirement already satisfied: docutils in /usr/local/lib/python3.10/dist-packages (from python-daemon>=3.0.0->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (0.20.1)
Requirement already satisfied: six>=1.5 in /usr/local/lib/python3.10/dist-packages (from python-dateutil>=2.3->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.16.0)
Requirement already satisfied: text-unidecode>=1.3 in /usr/local/lib/python3.10/dist-packages (from python-slugify>=5.0->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.3)
Requirement already satisfied: greenlet!=0.4.17 in /usr/local/lib/python3.10/dist-packages (from sqlalchemy<2.0,>=1.4->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (2.0.2)
Requirement already satisfied: sqlparse>=0.4.2 in /usr/local/lib/python3.10/dist-packages (from apache-airflow-providers-common-sql->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (0.4.4)
Requirement already satisfied: aiohttp in /usr/local/lib/python3.10/dist-packages (from apache-airflow-providers-http->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (3.8.5)
Requirement already satisfied: requests-toolbelt in /usr/local/lib/python3.10/dist-packages (from apache-airflow-providers-http->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.0.0)
Requirement already satisfied: idna in /usr/local/lib/python3.10/dist-packages (from httpx->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (3.4)
Requirement already satisfied: httpcore<0.18.0,>=0.15.0 in /usr/local/lib/python3.10/dist-packages (from httpx->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (0.17.3)
Requirement already satisfied: certifi in /usr/local/lib/python3.10/dist-packages (from httpx->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (2023.7.22)
Requirement already satisfied: sniffio in /usr/local/lib/python3.10/dist-packages (from httpx->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.3.0)
Requirement already satisfied: opentelemetry-exporter-otlp-proto-grpc==1.15.0 in /usr/local/lib/python3.10/dist-packages (from opentelemetry-exporter-otlp->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.15.0)
Requirement already satisfied: opentelemetry-exporter-otlp-proto-http==1.15.0 in /usr/local/lib/python3.10/dist-packages (from opentelemetry-exporter-otlp->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.15.0)
Requirement already satisfied: googleapis-common-protos~=1.52 in /usr/local/lib/python3.10/dist-packages (from opentelemetry-exporter-otlp-proto-grpc==1.15.0->opentelemetry-exporter-otlp->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.60.0)
Requirement already satisfied: opentelemetry-sdk~=1.12 in /usr/local/lib/python3.10/dist-packages (from opentelemetry-exporter-otlp-proto-grpc==1.15.0->opentelemetry-exporter-otlp->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.15.0)
Requirement already satisfied: opentelemetry-proto==1.15.0 in /usr/local/lib/python3.10/dist-packages (from opentelemetry-exporter-otlp-proto-grpc==1.15.0->opentelemetry-exporter-otlp->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.15.0)
Requirement already satisfied: backoff<3.0.0,>=1.10.0 in /usr/local/lib/python3.10/dist-packages (from opentelemetry-exporter-otlp-proto-grpc==1.15.0->opentelemetry-exporter-otlp->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (2.2.1)
Requirement already satisfied: grpcio<2.0.0,>=1.0.0 in /usr/local/lib/python3.10/dist-packages (from opentelemetry-exporter-otlp-proto-grpc==1.15.0->opentelemetry-exporter-otlp->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.57.0)
Requirement already satisfied: protobuf<5.0,>=3.19 in /usr/local/lib/python3.10/dist-packages (from opentelemetry-proto==1.15.0->opentelemetry-exporter-otlp-proto-grpc==1.15.0->opentelemetry-exporter-otlp->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (4.24.1)
Requirement already satisfied: pycparser in /usr/local/lib/python3.10/dist-packages (from cffi>=1.12->cryptography>=0.9.3->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (2.21)
Requirement already satisfied: dnspython>=1.15.0 in /usr/local/lib/python3.10/dist-packages (from email-validator<2,>=1.0.5->flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (2.4.2)
Requirement already satisfied: pytz in /usr/local/lib/python3.10/dist-packages (from Flask-Babel<3,>=1->flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (2023.3)
Requirement already satisfied: Babel>=2.3 in /usr/local/lib/python3.10/dist-packages (from Flask-Babel<3,>=1->flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (2.12.1)
Requirement already satisfied: ordered-set<5,>4 in /usr/local/lib/python3.10/dist-packages (from Flask-Limiter<4,>3->flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (4.1.0)
Requirement already satisfied: limits>=2.8 in /usr/local/lib/python3.10/dist-packages (from Flask-Limiter<4,>3->flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (3.5.0)
Requirement already satisfied: anyio<5.0,>=3.0 in /usr/local/lib/python3.10/dist-packages (from httpcore<0.18.0,>=0.15.0->httpx->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (3.7.1)
Requirement already satisfied: h11<0.15,>=0.13 in /usr/local/lib/python3.10/dist-packages (from httpcore<0.18.0,>=0.15.0->httpx->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (0.14.0)
Requirement already satisfied: charset-normalizer<4,>=2 in /usr/local/lib/python3.10/dist-packages (from requests<3,>=2.9.1->connexion[flask]>=2.10.0->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (3.2.0)
Requirement already satisfied: urllib3<3,>=1.21.1 in /usr/local/lib/python3.10/dist-packages (from requests<3,>=2.9.1->connexion[flask]>=2.10.0->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (2.0.4)
Requirement already satisfied: async-timeout<5.0,>=4.0.0a3 in /usr/local/lib/python3.10/dist-packages (from aiohttp->apache-airflow-providers-http->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (4.0.3)
Requirement already satisfied: aiosignal>=1.1.2 in /usr/local/lib/python3.10/dist-packages (from aiohttp->apache-airflow-providers-http->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.3.1)
Requirement already satisfied: multidict<7.0,>=4.5 in /usr/local/lib/python3.10/dist-packages (from aiohttp->apache-airflow-providers-http->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (6.0.4)
Requirement already satisfied: yarl<2.0,>=1.0 in /usr/local/lib/python3.10/dist-packages (from aiohttp->apache-airflow-providers-http->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.9.2)
Requirement already satisfied: frozenlist>=1.1.1 in /usr/local/lib/python3.10/dist-packages (from aiohttp->apache-airflow-providers-http->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (1.4.0)
Requirement already satisfied: importlib-resources>=1.3 in /usr/local/lib/python3.10/dist-packages (from limits>=2.8->Flask-Limiter<4,>3->flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (6.0.1)
Requirement already satisfied: opentelemetry-semantic-conventions==0.36b0 in /usr/local/lib/python3.10/dist-packages (from opentelemetry-sdk~=1.12->opentelemetry-exporter-otlp-proto-grpc==1.15.0->opentelemetry-exporter-otlp->apache-airflow>=2.4.0->apache-airflow-providers-sftp) (0.36b0)
Installing collected packages: bcrypt, pynacl, paramiko, sshtunnel, apache-airflow-providers-ssh, apache-airflow-providers-sftp
Successfully installed apache-airflow-providers-sftp-4.5.0 apache-airflow-providers-ssh-3.7.1 bcrypt-4.0.1 paramiko-3.3.1 pynacl-1.5.0 sshtunnel-0.4.0
WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# pip3 install --upgrade apache-airflow-providers-celery
Collecting apache-airflow-providers-celery
  Downloading apache_airflow_providers_celery-3.3.2-py3-none-any.whl (31 kB)
Requirement already satisfied: celery<6,>=5.2.3 in /usr/local/lib/python3.10/dist-packages (from apache-airflow-providers-celery) (5.3.1)
Collecting flower>=1.0.0
  Downloading flower-2.0.1-py2.py3-none-any.whl (383 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 383.6/383.6 KB 250.7 kB/s eta 0:00:00
Requirement already satisfied: apache-airflow>=2.4.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow-providers-celery) (2.7.0)
Requirement already satisfied: google-re2>=1.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow-providers-celery) (1.1)
Requirement already satisfied: jinja2>=3.0.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (3.1.2)
Requirement already satisfied: opentelemetry-exporter-otlp in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.15.0)
Requirement already satisfied: apache-airflow-providers-common-sql in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.7.0)
Requirement already satisfied: asgiref in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (3.7.2)
Requirement already satisfied: werkzeug>=2.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (2.2.3)
Requirement already satisfied: configupdater>=3.1.1 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (3.1.1)
Requirement already satisfied: pathspec>=0.9.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (0.11.2)
Requirement already satisfied: linkify-it-py>=2.0.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (2.0.2)
Requirement already satisfied: cattrs>=22.1.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (23.1.2)
Requirement already satisfied: setproctitle>=1.1.8 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.3.2)
Requirement already satisfied: apache-airflow-providers-imap in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (3.3.0)
Requirement already satisfied: croniter>=0.3.17 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.4.1)
Requirement already satisfied: mdit-py-plugins>=0.3.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (0.4.0)
Requirement already satisfied: tabulate>=0.7.5 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (0.9.0)
Requirement already satisfied: markdown-it-py>=2.1.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (3.0.0)
Requirement already satisfied: python-nvd3>=0.15.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (0.15.0)
Requirement already satisfied: blinker in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.6.2)
Requirement already satisfied: flask-login>=0.6.2 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (0.6.2)
Requirement already satisfied: sqlalchemy<2.0,>=1.4 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.4.49)
Requirement already satisfied: rfc3339-validator>=0.1.4 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (0.1.4)
Requirement already satisfied: termcolor>=1.1.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (2.3.0)
Requirement already satisfied: dill>=0.2.2 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (0.3.7)
Requirement already satisfied: sqlalchemy-jsonfield>=1.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.0.1.post0)
Requirement already satisfied: gunicorn>=20.1.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (21.2.0)
Requirement already satisfied: pydantic<2.0.0,>=1.10.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.10.12)
Requirement already satisfied: rich>=12.4.4 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (13.5.2)
Requirement already satisfied: tenacity!=8.2.0,>=6.2.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (8.2.3)
Requirement already satisfied: pendulum>=2.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (2.1.2)
Requirement already satisfied: apache-airflow-providers-sqlite in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (3.4.3)
Requirement already satisfied: python-dateutil>=2.3 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (2.8.2)
Requirement already satisfied: deprecated>=1.2.13 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.2.14)
Requirement already satisfied: psutil>=4.2.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (5.9.5)
Requirement already satisfied: jsonschema>=4.18.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (4.19.0)
Requirement already satisfied: markdown>=3.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (3.4.4)
Requirement already satisfied: cryptography>=0.9.3 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (41.0.3)
Requirement already satisfied: marshmallow-oneofschema>=2.0.1 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (3.0.1)
Requirement already satisfied: packaging>=14.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (23.1)
Requirement already satisfied: attrs>=22.1.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (23.1.0)
Requirement already satisfied: rich-argparse>=1.0.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.3.0)
Requirement already satisfied: cron-descriptor>=1.2.24 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.4.0)
Requirement already satisfied: flask<2.3,>=2.2 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (2.2.5)
Requirement already satisfied: flask-session>=0.4.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (0.5.0)
Requirement already satisfied: colorlog<5.0,>=4.0.2 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (4.8.0)
Requirement already satisfied: python-daemon>=3.0.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (3.0.1)
Requirement already satisfied: httpx in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (0.24.1)
Requirement already satisfied: lazy-object-proxy in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.9.0)
Requirement already satisfied: itsdangerous>=2.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (2.1.2)
Requirement already satisfied: markupsafe>=1.1.1 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (2.1.3)
Requirement already satisfied: unicodecsv>=0.14.1 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (0.14.1)
Requirement already satisfied: apache-airflow-providers-ftp in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (3.5.0)
Requirement already satisfied: graphviz>=0.12 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (0.20.1)
Requirement already satisfied: pygments>=2.0.1 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (2.16.1)
Requirement already satisfied: alembic<2.0,>=1.6.3 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.11.3)
Requirement already satisfied: argcomplete>=1.10 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (3.1.1)
Requirement already satisfied: apache-airflow-providers-http in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (4.5.0)
Requirement already satisfied: pyjwt>=2.0.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (2.8.0)
Requirement already satisfied: typing-extensions>=4.0.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (4.7.1)
Requirement already satisfied: flask-caching>=1.5.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (2.0.2)
Requirement already satisfied: connexion[flask]>=2.10.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (2.14.2)
Requirement already satisfied: opentelemetry-api==1.15.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.15.0)
Requirement already satisfied: lockfile>=0.12.2 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (0.12.2)
Requirement already satisfied: flask-wtf>=0.15 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.1.1)
Requirement already satisfied: python-slugify>=5.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (8.0.1)
Requirement already satisfied: pluggy>=1.0 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.2.0)
Requirement already satisfied: flask-appbuilder==4.3.3 in /usr/local/lib/python3.10/dist-packages (from apache-airflow>=2.4.0->apache-airflow-providers-celery) (4.3.3)
Requirement already satisfied: Flask-SQLAlchemy<3,>=2.4 in /usr/local/lib/python3.10/dist-packages (from flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-celery) (2.5.1)
Requirement already satisfied: sqlalchemy-utils<1,>=0.32.21 in /usr/local/lib/python3.10/dist-packages (from flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-celery) (0.41.1)
Requirement already satisfied: email-validator<2,>=1.0.5 in /usr/local/lib/python3.10/dist-packages (from flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.3.1)
Requirement already satisfied: Flask-Limiter<4,>3 in /usr/local/lib/python3.10/dist-packages (from flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-celery) (3.4.0)
Requirement already satisfied: click<9,>=8 in /usr/local/lib/python3.10/dist-packages (from flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-celery) (8.1.7)
Requirement already satisfied: colorama<1,>=0.3.9 in /usr/local/lib/python3.10/dist-packages (from flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-celery) (0.4.6)
Requirement already satisfied: apispec[yaml]<7,>=6.0.0 in /usr/local/lib/python3.10/dist-packages (from flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-celery) (6.3.0)
Requirement already satisfied: prison<1.0.0,>=0.2.1 in /usr/local/lib/python3.10/dist-packages (from flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-celery) (0.2.1)
Requirement already satisfied: marshmallow-sqlalchemy<0.27.0,>=0.22.0 in /usr/local/lib/python3.10/dist-packages (from flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-celery) (0.26.1)
Requirement already satisfied: Flask-Babel<3,>=1 in /usr/local/lib/python3.10/dist-packages (from flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-celery) (2.0.0)
Requirement already satisfied: Flask-JWT-Extended<5.0.0,>=4.0.0 in /usr/local/lib/python3.10/dist-packages (from flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-celery) (4.5.2)
Requirement already satisfied: WTForms<4 in /usr/local/lib/python3.10/dist-packages (from flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-celery) (3.0.1)
Requirement already satisfied: marshmallow<4,>=3.18.0 in /usr/local/lib/python3.10/dist-packages (from flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-celery) (3.20.1)
Requirement already satisfied: setuptools>=16.0 in /usr/local/lib/python3.10/dist-packages (from opentelemetry-api==1.15.0->apache-airflow>=2.4.0->apache-airflow-providers-celery) (68.1.2)
Requirement already satisfied: billiard<5.0,>=4.1.0 in /usr/local/lib/python3.10/dist-packages (from celery<6,>=5.2.3->apache-airflow-providers-celery) (4.1.0)
Requirement already satisfied: tzdata>=2022.7 in /usr/local/lib/python3.10/dist-packages (from celery<6,>=5.2.3->apache-airflow-providers-celery) (2023.3)
Requirement already satisfied: click-plugins>=1.1.1 in /usr/local/lib/python3.10/dist-packages (from celery<6,>=5.2.3->apache-airflow-providers-celery) (1.1.1)
Requirement already satisfied: click-repl>=0.2.0 in /usr/local/lib/python3.10/dist-packages (from celery<6,>=5.2.3->apache-airflow-providers-celery) (0.3.0)
Requirement already satisfied: kombu<6.0,>=5.3.1 in /usr/local/lib/python3.10/dist-packages (from celery<6,>=5.2.3->apache-airflow-providers-celery) (5.3.1)
Requirement already satisfied: vine<6.0,>=5.0.0 in /usr/local/lib/python3.10/dist-packages (from celery<6,>=5.2.3->apache-airflow-providers-celery) (5.0.0)
Requirement already satisfied: click-didyoumean>=0.3.0 in /usr/local/lib/python3.10/dist-packages (from celery<6,>=5.2.3->apache-airflow-providers-celery) (0.3.0)
Collecting tornado<7.0.0,>=5.0.0
  Downloading tornado-6.3.3-cp38-abi3-manylinux_2_17_aarch64.manylinux2014_aarch64.whl (428 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 428.1/428.1 KB 247.3 kB/s eta 0:00:00
Collecting prometheus-client>=0.8.0
  Downloading prometheus_client-0.17.1-py3-none-any.whl (60 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 60.6/60.6 KB 339.7 kB/s eta 0:00:00
Collecting humanize
  Downloading humanize-4.8.0-py3-none-any.whl (117 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 117.1/117.1 KB 199.5 kB/s eta 0:00:00
Requirement already satisfied: pytz in /usr/local/lib/python3.10/dist-packages (from flower>=1.0.0->apache-airflow-providers-celery) (2023.3)
Requirement already satisfied: Mako in /usr/local/lib/python3.10/dist-packages (from alembic<2.0,>=1.6.3->apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.2.4)
Requirement already satisfied: exceptiongroup in /usr/local/lib/python3.10/dist-packages (from cattrs>=22.1.0->apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.1.3)
Requirement already satisfied: prompt-toolkit>=3.0.36 in /usr/local/lib/python3.10/dist-packages (from click-repl>=0.2.0->celery<6,>=5.2.3->apache-airflow-providers-celery) (3.0.39)
Requirement already satisfied: clickclick<21,>=1.2 in /usr/local/lib/python3.10/dist-packages (from connexion[flask]>=2.10.0->apache-airflow>=2.4.0->apache-airflow-providers-celery) (20.10.2)
Requirement already satisfied: requests<3,>=2.9.1 in /usr/local/lib/python3.10/dist-packages (from connexion[flask]>=2.10.0->apache-airflow>=2.4.0->apache-airflow-providers-celery) (2.31.0)
Requirement already satisfied: inflection<0.6,>=0.3.1 in /usr/local/lib/python3.10/dist-packages (from connexion[flask]>=2.10.0->apache-airflow>=2.4.0->apache-airflow-providers-celery) (0.5.1)
Requirement already satisfied: PyYAML<7,>=5.1 in /usr/local/lib/python3.10/dist-packages (from connexion[flask]>=2.10.0->apache-airflow>=2.4.0->apache-airflow-providers-celery) (6.0.1)
Requirement already satisfied: cffi>=1.12 in /usr/local/lib/python3.10/dist-packages (from cryptography>=0.9.3->apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.15.1)
Requirement already satisfied: wrapt<2,>=1.10 in /usr/local/lib/python3.10/dist-packages (from deprecated>=1.2.13->apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.15.0)
Requirement already satisfied: cachelib<0.10.0,>=0.9.0 in /usr/local/lib/python3.10/dist-packages (from flask-caching>=1.5.0->apache-airflow>=2.4.0->apache-airflow-providers-celery) (0.9.0)
Requirement already satisfied: jsonschema-specifications>=2023.03.6 in /usr/local/lib/python3.10/dist-packages (from jsonschema>=4.18.0->apache-airflow>=2.4.0->apache-airflow-providers-celery) (2023.7.1)
Requirement already satisfied: referencing>=0.28.4 in /usr/local/lib/python3.10/dist-packages (from jsonschema>=4.18.0->apache-airflow>=2.4.0->apache-airflow-providers-celery) (0.30.2)
Requirement already satisfied: rpds-py>=0.7.1 in /usr/local/lib/python3.10/dist-packages (from jsonschema>=4.18.0->apache-airflow>=2.4.0->apache-airflow-providers-celery) (0.9.2)
Requirement already satisfied: amqp<6.0.0,>=5.1.1 in /usr/local/lib/python3.10/dist-packages (from kombu<6.0,>=5.3.1->celery<6,>=5.2.3->apache-airflow-providers-celery) (5.1.1)
Requirement already satisfied: uc-micro-py in /usr/local/lib/python3.10/dist-packages (from linkify-it-py>=2.0.0->apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.0.2)
Requirement already satisfied: mdurl~=0.1 in /usr/local/lib/python3.10/dist-packages (from markdown-it-py>=2.1.0->apache-airflow>=2.4.0->apache-airflow-providers-celery) (0.1.2)
Requirement already satisfied: pytzdata>=2020.1 in /usr/local/lib/python3.10/dist-packages (from pendulum>=2.0->apache-airflow>=2.4.0->apache-airflow-providers-celery) (2020.1)
Requirement already satisfied: docutils in /usr/local/lib/python3.10/dist-packages (from python-daemon>=3.0.0->apache-airflow>=2.4.0->apache-airflow-providers-celery) (0.20.1)
Requirement already satisfied: six>=1.5 in /usr/local/lib/python3.10/dist-packages (from python-dateutil>=2.3->apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.16.0)
Requirement already satisfied: text-unidecode>=1.3 in /usr/local/lib/python3.10/dist-packages (from python-slugify>=5.0->apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.3)
Requirement already satisfied: greenlet!=0.4.17 in /usr/local/lib/python3.10/dist-packages (from sqlalchemy<2.0,>=1.4->apache-airflow>=2.4.0->apache-airflow-providers-celery) (2.0.2)
Requirement already satisfied: sqlparse>=0.4.2 in /usr/local/lib/python3.10/dist-packages (from apache-airflow-providers-common-sql->apache-airflow>=2.4.0->apache-airflow-providers-celery) (0.4.4)
Requirement already satisfied: aiohttp in /usr/local/lib/python3.10/dist-packages (from apache-airflow-providers-http->apache-airflow>=2.4.0->apache-airflow-providers-celery) (3.8.5)
Requirement already satisfied: requests-toolbelt in /usr/local/lib/python3.10/dist-packages (from apache-airflow-providers-http->apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.0.0)
Requirement already satisfied: sniffio in /usr/local/lib/python3.10/dist-packages (from httpx->apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.3.0)
Requirement already satisfied: idna in /usr/local/lib/python3.10/dist-packages (from httpx->apache-airflow>=2.4.0->apache-airflow-providers-celery) (3.4)
Requirement already satisfied: httpcore<0.18.0,>=0.15.0 in /usr/local/lib/python3.10/dist-packages (from httpx->apache-airflow>=2.4.0->apache-airflow-providers-celery) (0.17.3)
Requirement already satisfied: certifi in /usr/local/lib/python3.10/dist-packages (from httpx->apache-airflow>=2.4.0->apache-airflow-providers-celery) (2023.7.22)
Requirement already satisfied: opentelemetry-exporter-otlp-proto-grpc==1.15.0 in /usr/local/lib/python3.10/dist-packages (from opentelemetry-exporter-otlp->apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.15.0)
Requirement already satisfied: opentelemetry-exporter-otlp-proto-http==1.15.0 in /usr/local/lib/python3.10/dist-packages (from opentelemetry-exporter-otlp->apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.15.0)
Requirement already satisfied: backoff<3.0.0,>=1.10.0 in /usr/local/lib/python3.10/dist-packages (from opentelemetry-exporter-otlp-proto-grpc==1.15.0->opentelemetry-exporter-otlp->apache-airflow>=2.4.0->apache-airflow-providers-celery) (2.2.1)
Requirement already satisfied: googleapis-common-protos~=1.52 in /usr/local/lib/python3.10/dist-packages (from opentelemetry-exporter-otlp-proto-grpc==1.15.0->opentelemetry-exporter-otlp->apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.60.0)
Requirement already satisfied: opentelemetry-sdk~=1.12 in /usr/local/lib/python3.10/dist-packages (from opentelemetry-exporter-otlp-proto-grpc==1.15.0->opentelemetry-exporter-otlp->apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.15.0)
Requirement already satisfied: opentelemetry-proto==1.15.0 in /usr/local/lib/python3.10/dist-packages (from opentelemetry-exporter-otlp-proto-grpc==1.15.0->opentelemetry-exporter-otlp->apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.15.0)
Requirement already satisfied: grpcio<2.0.0,>=1.0.0 in /usr/local/lib/python3.10/dist-packages (from opentelemetry-exporter-otlp-proto-grpc==1.15.0->opentelemetry-exporter-otlp->apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.57.0)
Requirement already satisfied: protobuf<5.0,>=3.19 in /usr/local/lib/python3.10/dist-packages (from opentelemetry-proto==1.15.0->opentelemetry-exporter-otlp-proto-grpc==1.15.0->opentelemetry-exporter-otlp->apache-airflow>=2.4.0->apache-airflow-providers-celery) (4.24.1)
Requirement already satisfied: pycparser in /usr/local/lib/python3.10/dist-packages (from cffi>=1.12->cryptography>=0.9.3->apache-airflow>=2.4.0->apache-airflow-providers-celery) (2.21)
Requirement already satisfied: dnspython>=1.15.0 in /usr/local/lib/python3.10/dist-packages (from email-validator<2,>=1.0.5->flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-celery) (2.4.2)
Requirement already satisfied: Babel>=2.3 in /usr/local/lib/python3.10/dist-packages (from Flask-Babel<3,>=1->flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-celery) (2.12.1)
Requirement already satisfied: ordered-set<5,>4 in /usr/local/lib/python3.10/dist-packages (from Flask-Limiter<4,>3->flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-celery) (4.1.0)
Requirement already satisfied: limits>=2.8 in /usr/local/lib/python3.10/dist-packages (from Flask-Limiter<4,>3->flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-celery) (3.5.0)
Requirement already satisfied: anyio<5.0,>=3.0 in /usr/local/lib/python3.10/dist-packages (from httpcore<0.18.0,>=0.15.0->httpx->apache-airflow>=2.4.0->apache-airflow-providers-celery) (3.7.1)
Requirement already satisfied: h11<0.15,>=0.13 in /usr/local/lib/python3.10/dist-packages (from httpcore<0.18.0,>=0.15.0->httpx->apache-airflow>=2.4.0->apache-airflow-providers-celery) (0.14.0)
Requirement already satisfied: wcwidth in /usr/local/lib/python3.10/dist-packages (from prompt-toolkit>=3.0.36->click-repl>=0.2.0->celery<6,>=5.2.3->apache-airflow-providers-celery) (0.2.6)
Requirement already satisfied: urllib3<3,>=1.21.1 in /usr/local/lib/python3.10/dist-packages (from requests<3,>=2.9.1->connexion[flask]>=2.10.0->apache-airflow>=2.4.0->apache-airflow-providers-celery) (2.0.4)
Requirement already satisfied: charset-normalizer<4,>=2 in /usr/local/lib/python3.10/dist-packages (from requests<3,>=2.9.1->connexion[flask]>=2.10.0->apache-airflow>=2.4.0->apache-airflow-providers-celery) (3.2.0)
Requirement already satisfied: aiosignal>=1.1.2 in /usr/local/lib/python3.10/dist-packages (from aiohttp->apache-airflow-providers-http->apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.3.1)
Requirement already satisfied: yarl<2.0,>=1.0 in /usr/local/lib/python3.10/dist-packages (from aiohttp->apache-airflow-providers-http->apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.9.2)
Requirement already satisfied: frozenlist>=1.1.1 in /usr/local/lib/python3.10/dist-packages (from aiohttp->apache-airflow-providers-http->apache-airflow>=2.4.0->apache-airflow-providers-celery) (1.4.0)
Requirement already satisfied: multidict<7.0,>=4.5 in /usr/local/lib/python3.10/dist-packages (from aiohttp->apache-airflow-providers-http->apache-airflow>=2.4.0->apache-airflow-providers-celery) (6.0.4)
Requirement already satisfied: async-timeout<5.0,>=4.0.0a3 in /usr/local/lib/python3.10/dist-packages (from aiohttp->apache-airflow-providers-http->apache-airflow>=2.4.0->apache-airflow-providers-celery) (4.0.3)
Requirement already satisfied: importlib-resources>=1.3 in /usr/local/lib/python3.10/dist-packages (from limits>=2.8->Flask-Limiter<4,>3->flask-appbuilder==4.3.3->apache-airflow>=2.4.0->apache-airflow-providers-celery) (6.0.1)
Requirement already satisfied: opentelemetry-semantic-conventions==0.36b0 in /usr/local/lib/python3.10/dist-packages (from opentelemetry-sdk~=1.12->opentelemetry-exporter-otlp-proto-grpc==1.15.0->opentelemetry-exporter-otlp->apache-airflow>=2.4.0->apache-airflow-providers-celery) (0.36b0)
Installing collected packages: tornado, prometheus-client, humanize, flower, apache-airflow-providers-celery
Successfully installed apache-airflow-providers-celery-3.3.2 flower-2.0.1 humanize-4.8.0 prometheus-client-0.17.1 tornado-6.3.3
WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# 
root@2a2814f91f18:~/airflow# airflow celery worker
/usr/local/lib/python3.10/dist-packages/airflow/configuration.py:799 FutureWarning: Bad scheme in Airflow configuration core > sql_alchemy_conn: `postgres`. As of SQLAlchemy 1.4 (adopted in Airflow 2.3) this is no longer supported.  You must change to `postgresql` before the next Airflow release.
[2023-08-23T19:16:59.164+0000] {configuration.py:2053} INFO - Creating new FAB webserver config file in: /root/airflow/webserver_config.py
[2023-08-23 19:16:59 +0000] [4292] [INFO] Starting gunicorn 21.2.0
[2023-08-23 19:16:59 +0000] [4292] [INFO] Listening at: http://[::]:8793 (4292)
[2023-08-23 19:16:59 +0000] [4292] [INFO] Using worker: sync
[2023-08-23 19:16:59 +0000] [4293] [INFO] Booting worker with pid: 4293
[2023-08-23 19:16:59 +0000] [4294] [INFO] Booting worker with pid: 4294
/usr/local/lib/python3.10/dist-packages/celery/platforms.py:829 SecurityWarning: You're running the worker with superuser privileges: this is
absolutely not recommended!

Please specify a different user using the --uid option.

User information: uid=0 euid=0 gid=0 egid=0

 
 -------------- celery@2a2814f91f18 v5.3.1 (emerald-rush)
--- ***** ----- 
-- ******* ---- Linux-5.15.49-linuxkit-pr-aarch64-with-glibc2.35 2023-08-23 19:16:59
- *** --- * --- 
- ** ---------- [config]
- ** ---------- .> app:         airflow.providers.celery.executors.celery_executor:0xffff92f1ef50
- ** ---------- .> transport:   amqp://guest:**@172.17.0.4:5672//
- ** ---------- .> results:     postgresql://postgres:**@172.17.0.3:5432/postgres
- *** --- * --- .> concurrency: 16 (prefork)
-- ******* ---- .> task events: OFF (enable -E to monitor tasks in this worker)
--- ***** ----- 
 -------------- [queues]
                .> default          exchange=default(direct) key=default
                

[tasks]
  . airflow.providers.celery.executors.celery_executor_utils.execute_command

[2023-08-23 19:17:00,742: WARNING/MainProcess] /usr/local/lib/python3.10/dist-packages/celery/worker/consumer/consumer.py:498: CPendingDeprecationWarning: The broker_connection_retry configuration setting will no longer determine
whether broker connection retries are made during startup in Celery 6.0 and above.
If you wish to retain the existing behavior for retrying connections on startup,
you should set broker_connection_retry_on_startup to True.
  warnings.warn(

[2023-08-23 19:17:00,751: INFO/MainProcess] Connected to amqp://guest:**@172.17.0.4:5672//
[2023-08-23 19:17:00,751: WARNING/MainProcess] /usr/local/lib/python3.10/dist-packages/celery/worker/consumer/consumer.py:498: CPendingDeprecationWarning: The broker_connection_retry configuration setting will no longer determine
whether broker connection retries are made during startup in Celery 6.0 and above.
If you wish to retain the existing behavior for retrying connections on startup,
you should set broker_connection_retry_on_startup to True.
  warnings.warn(

[2023-08-23 19:17:00,753: INFO/MainProcess] mingle: searching for neighbors
[2023-08-23 19:17:01,789: INFO/MainProcess] mingle: sync with 1 nodes
[2023-08-23 19:17:01,791: INFO/MainProcess] mingle: sync complete
[2023-08-23 19:17:01,814: INFO/MainProcess] celery@2a2814f91f18 ready.
[2023-08-23 19:18:39,983: INFO/MainProcess] Task airflow.providers.celery.executors.celery_executor_utils.execute_command[70757845-47c9-41ad-b8bc-3090fe34a9ce] received
[2023-08-23 19:18:40,134: INFO/ForkPoolWorker-16] [70757845-47c9-41ad-b8bc-3090fe34a9ce] Executing command in Celery: ['airflow', 'tasks', 'run', 'hello_dag', 'test', 'manual__2023-08-23T19:18:39.881505+00:00', '--local', '--subdir', 'DAGS_FOLDER/hello.py']
[2023-08-23 19:18:40,176: INFO/ForkPoolWorker-16] Filling up the DagBag from /opt/airflow/dags/hello.py
[2023-08-23 19:18:40,324: WARNING/ForkPoolWorker-16] Changing /root/airflow/logs/dag_id=hello_dag/run_id=manual__2023-08-23T19:18:39.881505+00:00/task_id=test permission to 509
[2023-08-23 19:18:40,327: INFO/ForkPoolWorker-16] Running <TaskInstance: hello_dag.test manual__2023-08-23T19:18:39.881505+00:00 [queued]> on host 2a2814f91f18
[2023-08-23 19:18:40,574: INFO/ForkPoolWorker-16] Task airflow.providers.celery.executors.celery_executor_utils.execute_command[70757845-47c9-41ad-b8bc-3090fe34a9ce] succeeded in 0.5739733750006053s: None
[2023-08-23 19:20:33,508: INFO/MainProcess] Task airflow.providers.celery.executors.celery_executor_utils.execute_command[f55bd199-dbdd-4eed-b471-fe97328f6c98] received
[2023-08-23 19:20:33,511: INFO/ForkPoolWorker-16] [f55bd199-dbdd-4eed-b471-fe97328f6c98] Executing command in Celery: ['airflow', 'tasks', 'run', 'hello_dag', 'test', 'manual__2023-08-23T19:20:33.321003+00:00', '--local', '--subdir', 'DAGS_FOLDER/hello.py']
[2023-08-23 19:20:33,516: INFO/MainProcess] Task airflow.providers.celery.executors.celery_executor_utils.execute_command[0c0ffbeb-1d13-4a67-869b-ae84e0b9ef73] received
[2023-08-23 19:20:33,573: INFO/ForkPoolWorker-16] Filling up the DagBag from /opt/airflow/dags/hello.py
[2023-08-23 19:20:33,652: INFO/ForkPoolWorker-1] [0c0ffbeb-1d13-4a67-869b-ae84e0b9ef73] Executing command in Celery: ['airflow', 'tasks', 'run', 'hello_dag', 'test2', 'manual__2023-08-23T19:20:33.321003+00:00', '--local', '--subdir', 'DAGS_FOLDER/hello.py']
[2023-08-23 19:20:33,658: ERROR/ForkPoolWorker-16] [f55bd199-dbdd-4eed-b471-fe97328f6c98] Failed to execute task Task test not found.
Traceback (most recent call last):
  File "/usr/local/lib/python3.10/dist-packages/airflow/providers/celery/executors/celery_executor_utils.py", line 156, in _execute_in_fork
    args.func(args)
  File "/usr/local/lib/python3.10/dist-packages/airflow/cli/cli_config.py", line 49, in command
    return func(*args, **kwargs)
  File "/usr/local/lib/python3.10/dist-packages/airflow/utils/cli.py", line 113, in wrapper
    return f(*args, **kwargs)
  File "/usr/local/lib/python3.10/dist-packages/airflow/cli/commands/task_command.py", line 409, in task_run
    task = _dag.get_task(task_id=args.task_id)
  File "/usr/local/lib/python3.10/dist-packages/airflow/models/dag.py", line 2472, in get_task
    raise TaskNotFound(f"Task {task_id} not found")
airflow.exceptions.TaskNotFound: Task test not found
[2023-08-23 19:20:33,680: ERROR/ForkPoolWorker-16] Task airflow.providers.celery.executors.celery_executor_utils.execute_command[f55bd199-dbdd-4eed-b471-fe97328f6c98] raised unexpected: AirflowException('Celery command failed on host: 2a2814f91f18 with celery_task_id f55bd199-dbdd-4eed-b471-fe97328f6c98')
Traceback (most recent call last):
  File "/usr/local/lib/python3.10/dist-packages/celery/app/trace.py", line 477, in trace_task
    R = retval = fun(*args, **kwargs)
  File "/usr/local/lib/python3.10/dist-packages/celery/app/trace.py", line 760, in __protected_call__
    return self.run(*args, **kwargs)
  File "/usr/local/lib/python3.10/dist-packages/airflow/providers/celery/executors/celery_executor_utils.py", line 122, in execute_command
    _execute_in_fork(command_to_exec, celery_task_id)
  File "/usr/local/lib/python3.10/dist-packages/airflow/providers/celery/executors/celery_executor_utils.py", line 137, in _execute_in_fork
    raise AirflowException(msg)
airflow.exceptions.AirflowException: Celery command failed on host: 2a2814f91f18 with celery_task_id f55bd199-dbdd-4eed-b471-fe97328f6c98
[2023-08-23 19:20:33,695: INFO/ForkPoolWorker-1] Filling up the DagBag from /opt/airflow/dags/hello.py
[2023-08-23 19:20:33,800: WARNING/ForkPoolWorker-1] Changing /root/airflow/logs/dag_id=hello_dag/run_id=manual__2023-08-23T19:20:33.321003+00:00/task_id=test2 permission to 509
[2023-08-23 19:20:33,803: INFO/ForkPoolWorker-1] Running <TaskInstance: hello_dag.test2 manual__2023-08-23T19:20:33.321003+00:00 [queued]> on host 2a2814f91f18
[2023-08-23 19:20:34,098: INFO/ForkPoolWorker-1] Task airflow.providers.celery.executors.celery_executor_utils.execute_command[0c0ffbeb-1d13-4a67-869b-ae84e0b9ef73] succeeded in 0.5786153340004603s: None
[2023-08-23 19:21:17,866: INFO/MainProcess] Task airflow.providers.celery.executors.celery_executor_utils.execute_command[a9ac43b3-2649-4a76-9750-f4113c795530] received
[2023-08-23 19:21:17,867: INFO/MainProcess] Task airflow.providers.celery.executors.celery_executor_utils.execute_command[4c2c7f35-69e1-420f-afee-267586cde5bd] received
[2023-08-23 19:21:17,875: INFO/ForkPoolWorker-1] [4c2c7f35-69e1-420f-afee-267586cde5bd] Executing command in Celery: ['airflow', 'tasks', 'run', 'hello_dag', 'test2', 'manual__2023-08-23T19:21:17.786482+00:00', '--local', '--subdir', 'DAGS_FOLDER/hello.py']
[2023-08-23 19:21:17,883: INFO/ForkPoolWorker-16] [a9ac43b3-2649-4a76-9750-f4113c795530] Executing command in Celery: ['airflow', 'tasks', 'run', 'hello_dag', 'test1', 'manual__2023-08-23T19:21:17.786482+00:00', '--local', '--subdir', 'DAGS_FOLDER/hello.py']
[2023-08-23 19:21:17,928: INFO/ForkPoolWorker-1] Filling up the DagBag from /opt/airflow/dags/hello.py
[2023-08-23 19:21:17,928: INFO/ForkPoolWorker-16] Filling up the DagBag from /opt/airflow/dags/hello.py
[2023-08-23 19:21:18,095: WARNING/ForkPoolWorker-1] Changing /root/airflow/logs/dag_id=hello_dag/run_id=manual__2023-08-23T19:21:17.786482+00:00/task_id=test2 permission to 509
[2023-08-23 19:21:18,096: INFO/ForkPoolWorker-1] Running <TaskInstance: hello_dag.test2 manual__2023-08-23T19:21:17.786482+00:00 [queued]> on host 2a2814f91f18
[2023-08-23 19:21:18,109: WARNING/ForkPoolWorker-16] Changing /root/airflow/logs/dag_id=hello_dag/run_id=manual__2023-08-23T19:21:17.786482+00:00/task_id=test1 permission to 509
[2023-08-23 19:21:18,109: INFO/ForkPoolWorker-16] Running <TaskInstance: hello_dag.test1 manual__2023-08-23T19:21:17.786482+00:00 [queued]> on host 2a2814f91f18
[2023-08-23 19:21:18,413: INFO/ForkPoolWorker-16] Task airflow.providers.celery.executors.celery_executor_utils.execute_command[a9ac43b3-2649-4a76-9750-f4113c795530] succeeded in 0.5430523340000946s: None
[2023-08-23 19:21:18,416: INFO/ForkPoolWorker-1] Task airflow.providers.celery.executors.celery_executor_utils.execute_command[4c2c7f35-69e1-420f-afee-267586cde5bd] succeeded in 0.5476822919999904s: None







[2023-08-23 19:21:37,194: INFO/MainProcess] sync with celery@9d00e02b0952
[2023-08-23 19:21:46,177: INFO/MainProcess] Task airflow.providers.celery.executors.celery_executor_utils.execute_command[2e88f910-8f83-4c1b-ba29-236857213c28] received
[2023-08-23 19:21:46,182: INFO/ForkPoolWorker-16] [2e88f910-8f83-4c1b-ba29-236857213c28] Executing command in Celery: ['airflow', 'tasks', 'run', 'hello_dag', 'test1', 'manual__2023-08-23T19:21:45.011362+00:00', '--local', '--subdir', 'DAGS_FOLDER/hello.py']
[2023-08-23 19:21:46,214: INFO/ForkPoolWorker-16] Filling up the DagBag from /opt/airflow/dags/hello.py
[2023-08-23 19:21:46,327: WARNING/ForkPoolWorker-16] Changing /root/airflow/logs/dag_id=hello_dag/run_id=manual__2023-08-23T19:21:45.011362+00:00/task_id=test1 permission to 509
[2023-08-23 19:21:46,328: INFO/ForkPoolWorker-16] Running <TaskInstance: hello_dag.test1 manual__2023-08-23T19:21:45.011362+00:00 [queued]> on host 2a2814f91f18
[2023-08-23 19:21:46,570: INFO/ForkPoolWorker-16] Task airflow.providers.celery.executors.celery_executor_utils.execute_command[2e88f910-8f83-4c1b-ba29-236857213c28] succeeded in 0.3918085830000564s: None











