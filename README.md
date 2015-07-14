# Ketaka Docker #

### Prerequisite ###

* docker - Read docker installation guide in doc/ and install it. ( [osx](https://github.com/kmsheng/ketaka-docker/blob/master/doc/docker-installation-guide-osx.md) / [ubuntu](https://github.com/kmsheng/ketaka-docker/blob/master/doc/docker-installation-guide-ubuntu.md) )
* ksana-cli
```bash
sudo npm install -g ksana-cli
```

### Installation ###

* This repo should be cloned in /Users if you're OSX user.
```bash
git submodule init
git submodule update
cd nginx-php5/ketaka/
npm install
ks server # press ctrl + c to stop ks server, this creates bundle.js and bundle.js.map
```
* Replace kangyur\_images/ folder in nginx-php5/ ( the real one should have more than 5G in size )
* Put jiangkangyur.kdb in nginx-php5/ketaka/
* Put database folder in pouchdb/database/ ( was in /usr/local/Cellar/nginx/x.x.x/html/ketaka/database according to [this](https://github.com/karmapa17/ketaka) )

### Start Ketaka Web Server ###

#### Create nginx/php5-fpm container ####
Note: if you are using boot2docker, the web server ip will be boot2docker's ip, not localhost. 
```bash
cd nginx-php5/
docker run --name web -v "$PWD:/usr/share/nginx/html" \
-v "$PWD/nginx.conf:/etc/nginx/nginx.conf" -v "$PWD/www.conf:/etc/php5/fpm/pool.d/www.conf" \
-p 80:80 -d kmsheng/nginx-php5:0.0.1
```
### Create pouchdb container ###
```bash
cd pouchdb/
docker run --name pouchdb -v "$PWD/database:/database" -p 5984:5984 -d kmsheng/pouchdb:0.0.1
```

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
