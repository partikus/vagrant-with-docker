Vagrant machine with Docker
===========================

### Requiremants
* [Virtual Box](https://www.virtualbox.org/wiki/Downloads)
* [Vagrant](https://www.vagrantup.com/downloads.html)

### Run machine
* Download machine from github `git clone https://github.com/jhryniuk/vagrant-with-docker.git`
* In console get inside location `vagrant-with-docker/`
* Run command `vagrant up`

### Checking machine
* After `vagrant up` run command `vagrant ssh` to get in the vagrant machine
* Run command `docker version`

You should get screen like that:

```
 Client:
 Version:      1.10.3
 API version:  1.22
 Go version:   go1.5.3
 Git commit:   20f81dd
 Built:        Thu Mar 10 15:54:52 2016
 OS/Arch:      linux/amd64

Server:
 Version:      1.10.3
 API version:  1.22
 Go version:   go1.5.3
 Git commit:   20f81dd
 Built:        Thu Mar 10 15:54:52 2016
 OS/Arch:      linux/amd64 
```

### Shutting down
* Get out from virtual machine by using `exit`
* Run command `vagrant halt`