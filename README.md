# Ketaka Docker #

### Prerequisite ###

* docker - Read docker installation guide in doc/ and install it.
* ksana-cli - Run "npm install -g ksana-cli" ( need sudo on Linux and Mac system )

### Installation ###

```bash
git submodule init
git submodule update
cd nginx-php5/ketaka/
npm install
ks server # and press ctrl + c to stop ks server. This creates bundle.js and bundle.js.map
```
* Replace kangyur\_images/ folder in nginx-php5/ ( the real one should have more than 5G in size )
* Put jiangkangyur.kdb in nginx-php5/ketaka/

### Start Ketaka Web Server ###

* cd in nginx-php5/
* docker run --name web -v "$PWD:/usr/share/nginx/html" \
  -v "$PWD/nginx.conf:/etc/nginx/nginx.conf" -v "$PWD/www.conf:/etc/php5/fpm/pool.d/www.conf" \
  -p 80:80 -d kmsheng/nginx-php5:0.0.1

* cd in pouchdb/
* docker run --name pouchdb -v "$PWD/database:/database" -p 5984:5984 -d kmsheng/pouchdb:0.0.1

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
