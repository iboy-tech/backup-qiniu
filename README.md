## 七牛云备份脚本

自动上传网站文件到七牛云，并删除三天前的旧备份

用python实现，需要依赖库`qiniu`，以及用来打包的`zip`

## 食用方法

直接使用git clone整个库

`git clone https://github.com/kzw200015/backup-qiniu.git`

安装 python 环境

`apt install -y python3`

进入脚本目录

`cd /root/backup-qiniu`

安装依赖

`apt install -y python3-pip`

`pip3 install qiniu`

按照脚本内的说明进行配置

执行脚本

`./main.py`

## 定时任务
用`cron`实现
执行`crontab -e`，加入以下内容
```
LANG='UTC-8'
LC_ALL='en_US.UTF-8'
0 2 * * * /root/backup-qiniu/main.py
```
保存退出即可，这样每天凌晨两点就会自动执行一次任务