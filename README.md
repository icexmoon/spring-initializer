# spring-initializer

# 能做什么

从 Spring 官网下载并解压以生成 spring boot 框架代码。

# 存在的意义

一般通过 Idea 从 https://start.spring.io/ 下载框架代码，但很诡异的是，经常会出现浏览器可以访问，但 Idea 无法下载的问题，尝试通过 curl 等 Linux 命令行 web 客户端下载，依然有概率出现连接超时的问题。

网上给出的解决方案是将 Spring 官网源替换为阿里源，我本来也打算这么干，但发现阿里源使用的是过时版本，版本支持上与官网不一致，因此就有了这个工具。

本工具的旨在通过其它方式无法快速下载 Spring 框架代码时，可以通过这个工具从官网下载，工具内设置了超时重试机制，默认是尝试10次，每次 2s 超时后重新尝试。

下载完后会自动解压，解压完成后会删除原始压缩包。

使用这个工具的另一个好处是可以扩展框架代码部署行为，比如最近几个版本的 Spring 中默认的 Lombok 存在 bug，需要将其指定为最新版，每次创建项目都要来这么一下，否则运行就会报错，完全可以在这个工具中自定义 pom 修改逻辑，让修改 pom 自动化完成。当然，目前没有这个功能，等以后更新或者你自行 fork。

# 安装

本工具用 Python 编写，通过 pip 安装：

```
pip install spring-initializer
```

更新使用以下命令：

```
pip install --upgrade spring-initializer
```

# 使用

通过 Python 模块方式运行：

```
python -m spring_initializer
```

更推荐以短命令方式运行：

```
pysi
```

不使用任何参数执行命令，会在工作目录下生成一个`spring_demo`目录，框架代码部署在其中。默认生成的是 Maven 项目，包含（spring-web 和 lombok）这两个常用依赖，使用的 Java 语言级别是 21。

可以通过命令行参数修改默认行为，比如指定目录名或生成 Gradle 项目等，参数说明可以通过以下命令查看：

```
pysi -h
```

# 运行环境

原则上本工具支持多平台，但并未在 Linux/Mac OS 中经过充分验证。

# 问题反馈

可以给我发邮件：icexmoon@qq.com

或者通过 github：[Issues · icexmoon/spring-initializer](https://github.com/icexmoon/spring-initializer/issues)

# 更新记录

## 1.0.3

新增指定项目包名的功能

## 1.0.2

修复使用短命令时程序会执行两次的 bug

## 1.0.1

增加 Readme 说明

## 1.0.0

创建。

