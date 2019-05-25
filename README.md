切换Root用户 \
`sudo -i`

安装 Docker \
`wget -qO- https://get.docker.com/ | sh`

安装 ResilioSync 成功后访问 http://ip:8888 \
`docker run -d --name ResilioSync -p 8888:8888 -p 55555:55555 -v /root/resiliosync:/mnt/sync --restart always resilio/sync`

安装 CloudTorrent 成功后访问 http://ip:7777 \
`docker run -d --name CloudTorrent -p 7777:7777 -v /root/resiliosync/folders:/downloads --restart always jpillora/cloud-torrent --port 7777`

安装 WatchTower 自动更新Image \
`docker run -d --name Watchtower --restart always -v /var/run/docker.sock:/var/run/docker.sock v2tec/watchtower`

安装 Portainer 成功后访问 http://ip:9000 在线管理Docker \
`docker run -d --name Portainer -p 9000:9000 --restart=always -v /var/run/docker.sock:/var/run/docker.sock portainer/portainer`
