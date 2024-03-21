# easy ssl monitor

使用方法 Usage

1.在main.py同级目录下新建domains.txt文件，文件内容为需要查询的域名，每行一个。

Create a new domains.txt file in the same level directory as main.py with the contents of the domains to be queried, one per line.

```text
www.google.com
api.test.tech:1047
example.com
```

2.将飞书机器人的webhook地址设置到环境变量WEBHOOK，例如

Set the webhook address of the Feishu bot to the environment variable WEBHOOK, for example
```bash
echo "export WEBHOOK=<webhook>" | tee -a /etc/profile
source /etc/profile
```

3.定时任务执行main.py

Crontab task execute main.py
```bash
crontab -e
```
写入以下内容

Write the following content
```text
10 10 * * * /usr/bin/python3 /path/to/main.py
```
