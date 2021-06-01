# Maven

scope：依赖的范围，默认值是 compile

optional：标示该依赖是否可选，默认是 false。可以理解为，如果为 true，则表示该依赖不会传递下去，如果为false，则会传递下去。

exclusions：用来排除传递性依赖





**「compile 范围依赖」**

对主程序是否有效：有效

对测试程序是否有效：有效

是否参与打包：参与

是否参与部署：参与

典型例子：log4j

**「test 范围依赖」**

对主程序是否有效：无效

对测试程序是否有效：有效

是否参与打包：不参与

是否参与部署：不参与

典型例子：Junit

**「provided 范围依赖」**

对主程序是否有效：有效

对测试程序是否有效：有效

是否参与打包：不参与

是否参与部署：不参与

典型例子：servlet-api.jar，一般在发布到 服务器中，比如 tomcat，服务器会自带 servlet-api.jar 包，所以provided 范围依赖只在编译测试有效。

**「runtime 范围依赖」**：在测试、运行的时候依赖，在编译的时候不依赖。例如：JDBC 驱动，项目代码只需要 jdk 提供的 jdbc 接口，只有在执行测试和运行项目的时候才需要实现 jdbc 的功能。





#### 1. 创建maven项目

```bash
mvn archetype:generate -DgroupId=cn.nuaon -DartifactId=api -Dversion=1.0.0 -DinteractiveMode=false -Dpackage=cn.nuaon.api
```

#### 2. maven项目生成eclipse项目文件

```bash
mvn eclipse:eclipse
```

#### 3. maven项目生成idea项目文件

```bash
mvn idea:idea
```

#### 4. mvn命令跳过测试

```shell
# 测试类不会生成.class文件
mvn install -Dmaven.test.skip=true

# 测试类会生成.class文件
mvn install -DskipTests

# 将Jar文件安装到本地Maven中
mvn install:install-file -Dfile=jave-1.0.2.jar -DgroupId=it.sauronsoftware -DartifactId=jave -Dversion=1.0.2 -Dpackaging=jar
```





