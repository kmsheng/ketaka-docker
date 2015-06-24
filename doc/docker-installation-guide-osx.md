# osx installation guide #

### Installation ###

This installation tested on:
 - OSX Yosmite 10.10.3
 - Docker version 1.7.0, build 0baf609
 - Boot2Docker-cli version: v1.7.0 ( Git commit: 7d89508 )

* Go to the boo2docker/osx-installer release page - https://github.com/boot2docker/osx-installer/releases/tag/v1.7.0
* Download Boot2Docker by clicking Boot2Docker-x.x.x.pkg in the “Downloads” section.
* Install Boot2Docker by double-clicking the package.
* Run commnand “boot2docker start” in terminal
* Export the following variables to environment based on boot2docker’s terminal message
  Values of DOCKER_HOST and DOCKER_CERT_PATH may be varied.
  For example, my message is

"""
  # in my .zshrc file
  export DOCKER_HOST=tcp://192.168.59.103:2376
  export DOCKER_CERT_PATH=/Users/kmsheng/.boot2docker/certs/boot2docker-vm
  export DOCKER_TLS_VERIFY=1
"""

* Run "docker run hello-world" and "docker info" to make sure that your docker is installed properly.
* Run "boot2docker ip" to show boot2dockers vm ip
* make sure "/Users -mapall={HOST_USER}:staff {HOST_PRIVATE_IP}" is in /etc/exports
* make sure "nfs.server.mount.require_resv_port = 0" is in /etc/nfs.conf
* sudo nfsd start
* boot2docker ssh
* sudo umount /Users
* sudo /usr/local/etc/init.d/nfs-client start
* sudo mount {HOST_PRIVATE_IP}:/Users /Users -o rw,async,noatime,rsize=32768,wsize=32768,proto=tcp

### Things to be checked on every reboot ###

* boot2docker is up
* nfs in osx is up
* nfs client in boot2docker is up
