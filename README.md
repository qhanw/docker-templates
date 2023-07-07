# 快速实现Docker环境搭建

### 开始

```bash
git clone https://github.com/qhanw/docker-templates.git docker && cd docker && rm -rf .git
```

在根文件夹中，执行以下命名即可快速打开一个`nginx`本地环境的服务器：
```bash
cd nginx
docker compose up -d

```
> 注意：`docker-compose.yaml`文件中 volumes 映射配置中`/Users/qhan/Documents/workplace/sso-web/dist`需更改为你应用的文件地址。
>
> 映射地址可配置多个，通常情况下一个即可。
> 
> nginx 相关配置在`templates/default.conf.template`中进行配置

**其它容器环境类似，请参考对应容器镜像的相关文档。**

### Docker 容器操作
```bash
# -d 是 run 命令的参数，表示：后台运行容器，并返回容器 ID；
# 1. 启动容器 可不加 -d
docker compose up -d

# 2. 移除容器
docker compose down

# 3. 修改配置后需先移除容器，然后重启
docker compose down
docker compose up -d
#or
docker compose down && docker compose up -d

# 4. 重启容器
docker restart [服务名]

# 5.查看所有容器
docker ps -a
```