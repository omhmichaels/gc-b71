# Test Review

## Summary

### Centos8: "Failed"
* Tested with docker centos8. Script "pre_rpmbuild.sh" failed. Likely cause directory location assumptions in hardcoded file paths.
* Expected: Successful RPM creation
* Failed due to not being able to locate resources

* Steps to Reproduce:  
```

# Build Centos8 test image
docker build -t yummy-harmony-centos8 ./docker/centos8/

# Test 
docker run -exec yummy-harmony-centos8 /root/gc-b71/./pre_rpmbuild.sh 


# Build AmazonLinux Test Image
docker build -t yummy-harmony-amazonlinux2 ./docker/amazonlinux2/

# Test 
docker run -exec yummy-harmony-amazonlinux2 /root/gc-b71/./pre_rpmbuild.sh 





```
#### Centos8
[root@ab6bae442710 gc-b71]# ./pre_rpmbuild.sh 4.3

Installed:
  bzip2-1.0.6-26.el8.x86_64                                      
  dwz-0.12-10.el8.x86_64                                         
  efi-srpm-macros-3-3.el8.noarch                                 
  elfutils-0.185-1.el8.x86_64                                    
  gc-7.6.4-3.el8.x86_64                                          
  gdb-headless-8.2-16.el8.x86_64                                 
  ghc-srpm-macros-1.4.2-7.el8.noarch                             
  go-srpm-macros-2-17.el8.noarch                                 
  guile-5:2.0.14-7.el8.x86_64                                    
  libatomic_ops-7.6.2-3.el8.x86_64                               
  libbabeltrace-1.5.4-3.el8.x86_64                               
  libipt-1.6.1-8.el8.x86_64                                      
  libpkgconf-1.4.2-1.el8.x86_64                                  
  libtool-ltdl-2.4.6-25.el8.x86_64                               
  ocaml-srpm-macros-5-4.el8.noarch                               
  openblas-srpm-macros-2-2.el8.noarch                            
  patch-2.7.6-11.el8.x86_64                                      
  perl-srpm-macros-1-25.el8.noarch                               
  pkgconf-1.4.2-1.el8.x86_64                                     
  pkgconf-m4-1.4.2-1.el8.noarch                                  
  pkgconf-pkg-config-1.4.2-1.el8.x86_64                          
  python-rpm-macros-3-41.el8.noarch                              
  python-srpm-macros-3-41.el8.noarch                             
  python3-rpm-macros-3-41.el8.noarch                             
  qt5-srpm-macros-5.15.2-1.el8.noarch                            
  redhat-rpm-config-125-1.el8.noarch                             
  rpm-build-4.14.3-19.el8.x86_64                                 
  rpmdevtools-8.10-8.el8.noarch                                  
  rust-srpm-macros-5-2.el8.noarch                                
  unzip-6.0-45.el8_4.x86_64                                      
  zip-3.0-23.el8.x86_64                                          
  zstd-1.4.4-1.el8.x86_64                                        

./pre_rpmbuild.sh: line 16: cd: harmony: No such file or directory
grep: go.mod: No such file or directory
fatal: not a git repository (or any of the parent directories): .git
cp: cannot stat '/images/gc-b71/harmony-one.spec.template': No such file or directory
sed: can't read /root/rpmbuild/SPECS/harmony-one-4.3.spec: No such file or directory
sed: can't read /root/rpmbuild/SPECS/harmony-one-4.3.spec: No such file or directory
sed: can't read /root/rpmbuild/SPECS/harmony-one-4.3.spec: No such file or directory

#### Amazon Linux 2
```
3.4.3
  Installed: rpm-4.11.3-40.amzn2.0.6.x86_64 at 2021-08-24 19:04
  Built    : Amazon Linux at 2021-06-29 18:43
  Committed: Nikhil Dikshit <nikhildi@amazon.com> at 2021-06-28

  Installed: yum-3.4.3-158.amzn2.0.5.noarch at 2021-08-24 19:04
  Built    : Amazon Linux at 2021-02-25 18:33
  Committed: Robert Nickel <halfdime@amazon.com> at 2021-02-22
bash-4.2# # Gather sysinfo
bash-4.2# printf "\n------------\n"  > debug.txt
bash-4.2# cat /etc/os-release >> /tmp/debug.txt
f "\n------------\n" >> debug.txt
yum --version >> debug.txt 

# Test ./pre_rpmbuild.sh
printf "\n--bash-4.2# 
bash-4.2# printf "\n------------\n" >> debug.txt
bash-4.2# yum --version >> debug.txt 
bash-4.2# 
bash-4.2# # Test ./pre_rpmbuild.sh
bash-4.2# printf "\n------------\n" >> debug.txt
bash-4.2# ./pre_rpmbuild.sh 4.3

Warning: group RPM Development Tools does not exist.
Maybe run: yum groups mark install (see man yum)
Error: No packages in any requested group available to install or update
./pre_rpmbuild.sh: line 5: rpmdev-setuptree: command not found
./pre_rpmbuild.sh: line 7: cd: /root/rpmbuild/SOURCES/: No such file or directory
./pre_rpmbuild.sh: line 16: cd: harmony: No such file or directory
grep: go.mod: No such file or directory
fatal: No names found, cannot describe anything.
cp: cannot stat '/images/gc-b71/harmony-one.spec.template': No such file or directory
sed: can't read /root/rpmbuild/SPECS/harmony-one-4.3.spec: No such file or directory
sed: can't read /root/rpmbuild/SPECS/harmony-one-4.3.spec: No such file or directory
sed: can't read /root/rpmbuild/SPECS/harmony-one-4.3.spec: No such file or directory
./pre_rpmbuild.sh: line 26: cd: /root/rpmbuild/SOURCES/: No such file or directory
./pre_rpmbuild.sh: line 27: tar: command not found