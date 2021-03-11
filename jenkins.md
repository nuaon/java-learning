### Jenkins

安装步骤：

1. 下载Jenkins最新版 [WAR下载地址](http://mirrors.jenkins.io/war-stable/latest/jenkins.war)；
2. 运行命令：`java -jar jenkins.war --httpPort=9090`
3. 浏览http://localhost:9090并等到*Unlock Jenkins*页面出现。
4. 继续使用[Post-installation setup wizard](https://www.jenkins.io/zh/doc/book/installing/#setup-wizard)后面步骤设置向导。

不像在Docker中下载和运行有Blue Ocean的Jenkins，这个过程不会自动安装Blue Ocean功能， 这将分别需要在jenkins上通过 [**Manage Jenkins**](https://www.jenkins.io/zh/doc/book/managing) > [**Manage Plugins**](https://www.jenkins.io/zh/doc/book/managing/plugins/)安装。 在[Getting started with Blue Ocean](https://www.jenkins.io/zh/doc/book/blueocean/getting-started/)有关于安装Blue Ocean的详细信息 。

