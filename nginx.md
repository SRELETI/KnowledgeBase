## Notes on working with nginx web server (on CentOS 7)

#### 1. Installation

###### Prerequisite: Add the nginx epel repo to the system.

* Create a file named `nginx.repo` under `/etc/yum.repos.d/` directory and add
```
  [nginx]
  name=nginx repo
  baseurl=http://nginx.org/packages/OS/release/$basearch/
  gpgcheck=0
  enabled=1
```
> The OS should be linux distribution. In my case, it is `centos` and the release should be 5,6,7 for 5.x, 6.x, 7.x resp

###### Run `sudo yum install nginx`.

* This will install `nginx` on the system.

#### 2. Directory Structure

The directory structure for `nginx` is

* Configuration directory: `/etc/nginx/`
* Default Configuration file: `/etc/nginx/nginx.conf`
* Virutal Host Configuration file: `/etc/nginx/conf.d/`
* Custom Configuration file: `/etc/nginx/conf.d/`
* Logs(Access and error logs): `/var/log/nginx/`
* Default Virutal host files: `/usr/share/nginx/html/`
