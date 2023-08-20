## 👋 Welcome to ntfy 🚀  

ntfy README  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update ntfy
```
  
## Install and run container
  
```shell
mkdir -p "$HOME/.local/share/srv/docker/ntfy/rootfs"
git clone "https://github.com/dockermgr/ntfy" "$HOME/.local/share/CasjaysDev/dockermgr/ntfy"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/ntfy/rootfs/." "$HOME/.local/share/srv/docker/ntfy/rootfs/"
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-ntfy \
--hostname ntfy \
-e TZ=${TIMEZONE:-America/New_York} \
-v $HOME/.local/share/srv/docker/casjaysdevdocker-ntfy/rootfs/data:/data:z \
-v $HOME/.local/share/srv/docker/casjaysdevdocker-ntfy/rootfs/config:/config:z \
-p 80:80 \
casjaysdevdocker/ntfy:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdevdocker/ntfy
    container_name: casjaysdevdocker-ntfy
    environment:
      - TZ=America/New_York
      - HOSTNAME=ntfy
    volumes:
      - $HOME/.local/share/srv/docker/casjaysdevdocker-ntfy/rootfs/data:/data:z
      - $HOME/.local/share/srv/docker/casjaysdevdocker-ntfy/rootfs/config:/config:z
    ports:
      - 80:80
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdevdocker/ntfy
```
  
OR
  
```shell
git clone "https://github.com/casjaysdevdocker/ntfy" "$HOME/Projects/github/casjaysdevdocker/ntfy"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdevdocker/ntfy"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdevdocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/u/casjaysdevdocker) ⛵  
