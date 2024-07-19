# 常用docker工具
痛点：局域网，拥有外网权限的机器少
预期：对外网服务进行缓存

## dnsmasq:
局域网或者需代理上网的环境中可搭建的dns代理
dnsmasqhosts文件中可添加自定义hosts
```shell
[root@ceph01 ~]# cat /etc/resolv.conf
nameserver 192.168.1.111
```

## nginx:
简单启动nginx

## registry：
docker pull的代理
```shell
[root@control01 ~]# cat /etc/docker/daemon.json 
{
    "insecure-registries": [
        "172.16.10.91:8083"
    ],
    "log-opts": {
        "max-file": "5",
        "max-size": "50m"
    }
}
```

## squid:
代理缓存

## nexus3:
这个很全呼，等我后面谢谢
