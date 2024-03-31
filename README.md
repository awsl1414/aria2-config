# Aria2 Configures

自用aria2配置

## Sources

- Core: [aria2](https://github.com/aria2/aria2)
- HideRun.vbs: [p3terx](https://p3terx.com/archives/use-aria2-under-windows.html)
- aria2 client: [Aria2 & YAAW 使用说明](https://aria2c.com/usage.html)
	- [说明](#Aria2---CLI-Metalink/BitTorrent-Client)

## Files

### windows

    HideRun.vbs		隐藏运行
    Kill.vbs		结束运行
    aria2.conf		aria2配置
    aria2.log		日志
    aria2.session	进度(只保存未完成)
    aria2c.exe		core program
    dht.dat			DHT file
    dht6.dat		DHT file with ipv6

### linux

    aria2.conf		aria2配置
    aria2.log		日志
    aria2.session	进度(只保存未完成)
    dht.dat			DHT file
    dht6.dat		DHT file with ipv6

## How to use

### archlinux


```shell
sudo pacman -S aria2
```

```shell
git clone git@github.com:awsl1414/aria2-config.git
cp -r aria2-config/linux/.aria2 ~
```

```shell
# ~/.config/systemd/user/aria2.service
[Unit]
Description=Aria2 Daemon

[Service]
ExecStart=/usr/bin/aria2c --conf-path=/home/arch/.aria2/aria2.conf

[Install]
WantedBy=default.target
```

```shell
systemctl enable --user aria2.service
systemctl start --user aria2.service
systemctl stop --user aria2.service
systemctl status --user aria2.service
```
