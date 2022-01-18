# makefile_tutorial_project
- blog: https://zhuanlan.zhihu.com/p/396448133


# 实现http请求

实现目的：
1. 具体有两个依赖， openssl， libcurl
2. 存在include、libs依赖
3. 可以锻炼一个完整的相对完善的工程案例， 还可以锻炼代码调试

实现效果： 
1. 写一个程序，可以从任何网站上下载东西


## 下载软件
- openssL
- curl


## 编译openssl
```bash
# 配置文件。指定prefix， 让编译后的结果存储到指定目录
./config --prefix=/root/data/ros/Make_tutorial/Makefile_tutorial/level2/lean/openssl-1.1.1j 


# 编译所有后，执行安装， -j16代表16个线程执行操作
make all -j16 && make install -j16
```


## 编译curl

```bash
# 1. 配置文件。 
# --prefix: 让编译后的结果放到指定目录
# --with-openssl: 设置为curl依赖的openssl目录，指向刚才编译的文件
 ./config  --prefix=/root/data/ros/Make_tutorial/Makefile_tutorial/level2/lean/openssl-1.1.1j


## 2. 编译安装
```



## 配置IntellSense和browse路径
