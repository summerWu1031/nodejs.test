## 怎么用阿里云服务器去打开本地的项目
1. 登录账号 ssh username@阿里云上面公告的IP
   ```
   ssh frank@aliyun1
   ssh frank@8.129.237.221
   ```
   用管理者打开记事本，然后在记事本打开c/windows/system32/driver/etc/hosts
   然后在里面输入
   8.129.237.221 aliyun1
   把阿里云上面的IP，设置成一个名字，然后以后登录就可以直接ssh frank@aliyun1代替ssh frank@8.129.237.221

2. git clone https://github.con/xxx
   从GitHub下载该项目，要用https下载 不能用ssh

3. cd 到下载的文件

4. 封装运行命令，用./start代替node server.js 8888
   1. touch log
   2. node server.js 8888 > log 2>&1 &
   3. touch start
   4. echo 'node server.js 8888 > log 2>&1 &' >> start
   5. chmod +x ./start
   6. ./start 就可以运行

<br>

## 如何更新重启  
1. 本地更新完git push
2. 登录 ssh frank@aliyun1
3. cd 到该文件夹
4. git pull(把更新的内容下载)
5. killall node
6. ./start
   