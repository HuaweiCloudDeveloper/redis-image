# Redis部署指南

## ‌一、环境准备
### 系统配置
> -  服务器：鲲鹏服务器
> -  操作系统：Huawei Cloud EulerOS 2.0 64bit
> - CPU: 2vCPUs 或更高
> - RAM: 4GB 或更大
> - Disk: 至少 40GB
### 更新系统并安装依赖

```bash
sudo yum update -y  
sudo yum install -y git gcc-c++ make tcl wget  # 安装编译工具链‌:ml-citation{ref="3,7" data="citationList"}
```

## ‌二、源码下载与编译

### 1.下载 Redis 6.2.7 源码
```bash
wget https://download.redis.io/releases/redis-6.2.7.tar.gz  
tar xzf redis-6.2.7.tar.gz  
cd redis-6.2.7  
```

### 2.编译与安装
```bash
make -j$(nproc)  # 多线程编译（ARM 架构无需额外参数）‌:ml-citation{ref="3,7" data="citationList"}  
sudo make install PREFIX=/usr/local/redis  # 指定安装路径‌:ml-citation{ref="5,8" data="citationList"}  
```

## ‌三、配置与部署
### 1.创建配置文件目录
```bash
sudo mkdir -p /etc/redis /var/lib/redis  
sudo cp redis.conf /etc/redis/  
```
### 2.‌修改配置文件
```bash
sudo vim /etc/redis/redis.conf  
```
关键参数调整：
```text
bind 0.0.0.0  # 允许远程访问‌:ml-citation{ref="5,7" data="citationList"}  
daemonize yes  # 后台运行‌:ml-citation{ref="7" data="citationList"}  
dir /var/lib/redis  # 持久化数据目录‌:ml-citation{ref="7" data="citationList"}  
```
### 3.设置目录权限
```bash
sudo useradd redis  # 创建 Redis 用户  
sudo chown -R redis:redis /var/lib/redis  # 授权数据目录 ‌:ml-citation{ref="6,8" data="citationList"}  
```

### 4.添加 redis-cli 到系统路径
```bash
sudo cp /usr/local/redis/bin/redis-cli /usr/local/bin/  # 根据实际路径调整
```
##四、服务管理
###1.创建 Systemd 服务
```bash
sudo vim /etc/systemd/system/redis.service  # 新建服务文件 ‌:ml-citation{ref="6,8" data="citationList"}  
```
添加以下内容：
```text
[Unit]
Description=Redis Server  
After=network.target  

[Service]
Type=forking  
User=redis  
ExecStart=/usr/local/redis/bin/redis-server /etc/redis/redis.conf  
ExecStop=/usr/local/redis/bin/redis-cli shutdown  
Restart=on-failure  
RestartSec=5s  

[Install]
WantedBy=multi-user.target   
```

###2.启动与验证
####1.启动服务
```bash
sudo chmod 755 /etc/systemd/system/redis.service  # 确保服务文件可执行‌:ml-citation{ref="5" data="citationList"}  
sudo systemctl daemon-reload                       # 重新加载配置‌:ml-citation{ref="5,6" data="citationList"}  
sudo systemctl enable redis                        # 加入开机自启‌:ml-citation{ref="5,6" data="citationList"}  
sudo systemctl start redis                         # 立即启动服务‌:ml-citation{ref="5,6" data="citationList"}  
sudo systemctl status redis  # 检查运行状态 :ml-citation{ref="6,8" data="citationList"}  
```
####1.基础功能验证

‌检查服务状态
```bash
sudo systemctl status redis  # 确认状态为 `active (running)`‌:ml-citation{ref="8" data="citationList"}  
```

‌连接 Redis 并执行命令‌

```bash
redis-cli -p 6379  # 连接到默认端口‌:ml-citation{ref="2,7" data="citationList"}  
```
发送 PING 命令验证连通性：
```text
127.0.0.1:6379> PING  
"PONG"  # 返回 PONG 表示通信正常‌:ml-citation{ref="2,7" data="citationList"}  
```
测试键值操作：
```text
127.0.0.1:6379> SET test_key "hello"  
OK  
127.0.0.1:6379> GET test_key  
"hello"  
```