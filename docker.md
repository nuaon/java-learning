* 查看镜像
`docker images`

* 删除镜像
`docker rmi openapi`

* 查看当前运行的容器
`docker ps`

* 命令则会显示所有状态的容器（包括已经退出的）
`docker ps -a 或者 docker container ls -a`

* 删除所有container
`docker rm -f $(docker pa -aq)`

* 删除所有容器
`docker rm -f $(docker images)`

* 删除容器
`docker rm 容器ID`

* 构建docker镜像
`docker build -t openapi:1.0.5 .`

* 运行openapi镜像
`docker run -d --name openapi -p 11201:11201 openapi`

* 查看运行日志
`docker logs openapi`

* 打tag
`docker tag openapi zhougang/openapi:1.0.5`


* 登录阿里云镜像账号
`docker login --username=party_art@126.com registry.cn-hangzhou.aliyuns.com`

* 打tag
`docker tag openapi registry.cn-hangzhou.aliyuns.com/zhougang/openapi:1.0.5`

* 将镜像push到远程
`docker push registry.cn-hangzhou.aliyuns.com/zhougang/openapi:1.0.5`

* 拉取远程镜像
`docker pull registry.cn-hangzhou.aliyuns.com/zhougang/openapi:1.0.5`

* 运行镜像
`docker run -d --name openapi -p 11201:11201 registry.cn-hangzhou.aliyuns.com/zhougang/openapi:1.0.5`


* 进入容器
`docker exec -it 镜像id /bin/bash`

* 停止容器
`docker stop openapi`

* 如果想要快速停止容器，可以使用 docker kill 命令
`docker kill openapi`

* 重启容器
docker restart 可以重启容器，其作用就是依次执行 docker stop 和 docker start。

`docker restart openapi`


* 暂停/恢复容器
如果只是希望容器暂停工作一段时间，比如对容器的文件系统大打个快照，或者 docker host 需要使用 CPU，这是可以执行 docker pause 将其暂停。
`docker pause openapi`




* 查看资源占用情况
`docker stats openapi`