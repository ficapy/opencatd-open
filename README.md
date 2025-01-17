# opencatd-open
<a title="Docker Image CI" target="_blank" href="https://github.com/mirrors2/opencatd-open/actions"><img alt="GitHub Workflow Status" src="https://img.shields.io/github/actions/workflow/status/mirrors2/opencatd-open/ci.yaml?label=Actions&logo=github&style=flat-square"></a>
<a title="Docker Pulls" target="_blank" href="https://hub.docker.com/r/mirrors2/opencatd-open"><img src="https://img.shields.io/docker/pulls/mirrors2/opencatd-open.svg?logo=docker&label=docker&style=flat-square"></a>

OpenCat for Team的开源实现

基本实现了opencatd的全部功能

## 快速上手
```
docker run -d --name opencatd -p 80:80 -v /etc/opencatd:/app/db mirrors2/opencatd-open
```
## docker-compose

```
version: '3.7'
services: 
  opencatd:
    image: mirrors2/opencatd-open
    container_name: opencatd-open 
    restart: unless-stopped
    ports:
      - 80:80
    volumes:
      - /etc/opencatd:/app/db
    
```
or

```
wget https://github.com/mirrors2/opencatd-open/raw/main/docker/docker-compose.yml
```
## reset root token
```
docker exec -it opencatd-open ./opencatd reset_root
docker exec -it opencatd-open ./opencatd root_token
```

## Q&A
关于证书?
- docker部署会白白占用掉VPS的80，443很不河里,建议用Nginx/Caddy/Traefik等反代并自动管理HTTPS证书.

没有服务器?  
- 可以白嫖一些免费的容器托管服务:如:
  - [![Deploy on Railway](https://railway.app/button.svg)](https://railway.app/template/ppAoCV?referralCode=TW5RNa)
  - [Zeabur](https://zeabur.com/zh-CN)
  - [koyeb](https://koyeb.io/) 
  - [Fly.io](https://fly.io/)
  - 或者其他

# License

[GNU General Public License v3.0](License)
