# Create-local-repository
This repository contains instruction and example to create local repository on Linux

Why Local Repository?

- To avoid dependencies issue with package.
- Installing each dependency seaparately takes more time.

Step to Create Local Repository:

1. Prerequisites: createrepo package should be installed on linux. You can install createrepo package using below command:


  sudo yum install -y createrepo


2. create directory to keep all depedencies. 

  mkdir /apps_dir/


3. Download and keep all dependencies into that directories.

  ls /apps_dir/
  *.rpm


4. Run below command to generate repodata.


  sudo createrepo /apps_dir/


5. create file into /etc/ directory to create repo file


  sudo vi /etc/yum.repos.d/<repository_name>.repo

  [ <repository_name> ]
  
  baseurl = file://<rpm_path>
  
  enabled = 1
  
  gpgcheck = 0
  
  name = description

6. Once step 5 done we can install package without getting any depedencies issue


  sudo yum install -y <package_name>

