#### 下载mysql镜像，docker官网的镜像下载比较慢，这里是用网易蜂巢的镜像库

```
docker pull hub.c.163.com/library/mysql:5.6

```

#### 创建mysql本地存储目录

` mkdir -p ~/mysql/data `

#### 启动命令

```
docker run -p 3306:3306 --name mysql -v ~/mysql/data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=123456  -d hub.c.163.com/library/mysql:5.6

```
参数说明：

```
-p 3306:3306 是将docker 的3306端口映射到本机3306 端口
-v ~/mysql/data:/var/lib/mysql 是将docker的/var/lib/mysql 文件夹映射到本机的/mysql/data
-e MYSQL_ROOT_PASSWORD=123456 输入密码

```
修改密码：
```
注：（如果需要修改密码 执行docker -exec -it 容器id /bin/bash 进入容器修改密码，
修改后可以使用 docker commit 容器id 新名称 提交镜像修改。）

```

启动：

```
docker start mysql(创建的容器名称)
```
停止：
```
docker stop mysql
```
