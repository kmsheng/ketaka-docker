# Ketaka Docker #

### Prerequisite ###

* docker - Read docker installation guide in doc/ and install it.
* ksana-cli - Run "npm install -g ksana-cli" ( need sudo on Linux and Mac system )

### Installation ###

* This has been tested on
* Run "git submodule update" first
* cd in nginx/ketaka/ && npm install
* Run "ks server" and Ctrl + C to stop ks server. # Create bundle.js and bundle.js.map
* Replace kangyur\_images/ folder in nginx/ ( the real one should have more than 5G in size )
* Put jiangkangyur.kdb in nginx/ketaka/
* cd in nginx/

### Q & A ###

* What I do with the ip certification issue in osx ?
  - Run Vertualbox
  - Right click boot2docker-vm
  - Click close - power off
  - Run "boot2docker up" in terminal


### Useful Links ###

* [Official Docker Mac Installation Guide](https://docs.docker.com/installation/mac/)
* [Official Nginx Image](https://registry.hub.docker.com/_/nginx/)
* [Official Ubuntu Image](https://registry.hub.docker.com/_/ubuntu/)
* [Best practices for writing Dockerfiles](https://docs.docker.com/articles/dockerfile_best-practices/)
* [How to Use Docker on OS X: The Missing Guide](http://viget.com/extend/how-to-use-docker-on-os-x-the-missing-guide)
* [Use docker without sudo in ubuntu](http://askubuntu.com/questions/477551/how-can-i-use-docker-without-sudo)
* [Linking containers together](https://docs.docker.com/userguide/dockerlinks/)
* [AshWu's Docker Articles](http://blog.hsatac.net/categories/docker/)

### Contact ###

* 盛貫銘 kmsh3ng@gmail.com
