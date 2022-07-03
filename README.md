# Splendor

This is an homage to the board game [Splendor](https://boardgamegeek.com/boardgame/148228/splendor).

## Differences from the official game rules

There is only one known difference between this version and the official version of the game: in this version you are not allowed to spend gold gems if you have the correct color gem you are substituting for gold. In practice this affects games extremely rarely since in the vast majority of cases you would prefer not to spend your gold gems, but spending gold gems could theoretically be strategically correct to deny a certain chip pile.

## How to run

以下两种方式任选一种即可


### 1. 服务器部署

自行购买云服务器(比如腾讯云轻量级服务器等)

安装好`docker/docker-compose`等前置依赖后，在项目根目录下，即 `docker-compose.yml` 所在路径
执行:
```
docker-compose up
```

打开服务器防火墙的 8000 端口

然后各自访问该服务器 ip:8000 即可。

### 2.本地运行:

需要提前装好 `virtualenv`:
```
pip3 install virtualenv
```

然后:
```
./install.sh
```

然后启动:
```
ENV/bin/python server/splendor.py
或者
python3 server/splendor.py
```

- 局域网内对战方式:(两人共用一个 Wifi)

1P 本地打开 `127.0.0.1:8000`

随便填写房间号，然后创建游戏

![](img/wait.jpg)

把`127.0.0.1` 替换成 1P 的内网IP，然后把链接发给 2P, 

让 2P 访问 `内网ip:8000/房间名` 即可, 以我这里为例子，需要访问: `http://192.168.1.107:8000/Roundabout`

2P 点击页面右上角加入游戏后:

![](img/ready.jpg)

1P 点击开始游戏即可。

### 内网 IP 查询方式
- mac: `ifconfig | grep broadcast`

![](img/ip.jpg)
