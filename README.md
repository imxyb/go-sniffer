
# go-sniffer

> 捕获mysql,redis,http,mongodb等协议...完善中
> - 抓取项目中的数据库请求，如:执行的mysql查询语句
> - 不需要修改项目代码，通过指定端口抓包解析协议
> - 快速预览项目中所有的数据请求,便于程序调试

[![GitHub license](https://img.shields.io/github/license/40t/go-sniffer.svg?style=popout-square)](https://github.com/40t/go-sniffer/blob/master/LICENSE)



## Support List:
- [mysql](#mysql)
- [Redis](#redis)
- [Http](#http)
- [Mongodb](#mongodb)
- Kafka (developing)
- ...

## Demo:
``` bash
$ go-sniffer en0 mysql
```
![image](https://github.com/40t/go-sniffer/raw/master/images/demo.gif)
## Setup:
- 支持 : `MacOS` `Linux` `Unix`
- 不支持 : `windows`
- 依赖:`google/gopacket`库

### 依赖库安装：Centos
``` bash
$ yum install libcap-devel
```
### 依赖库安装: Ubuntu
``` bash
$ apt-get install libcap-dev
```
### RUN
``` bash
$ go get -v github.com/40t/go-sniffer
$ cd $(go env GOPATH)/src/github.com/40t/go-sniffer
$ go run main.go
```
## Usage:
``` bash
=======================================================================
[使用说明]

    go-sniffer [设备名] [插件名] [插件参数(可选)]

    [例子]
          go-sniffer en0 redis          抓取redis数据包
          go-sniffer en0 mysql -p 3306  抓取mysql数据包,端口3306

    go-sniffer --[命令]
               --help 帮助信息
               --env  环境变量
               --list 插件列表
               --ver  版本信息
               --dev  设备列表
    [例子]
          go-sniffer --list 查看可抓取的协议

=======================================================================
[设备名] : lo0 :   127.0.0.1
[设备名] : en0 : x:x:x:x:x5:x  192.168.1.3
[设备名] : utun2 :   1.1.11.1
=======================================================================
```

### mysql
> 支持预处理语句等常大部分语句
``` bash
$ go-sniffer [设备名] mysql [参数]
-p 置顶端口，默认3306
```
![image](https://github.com/40t/go-sniffer/raw/master/images/mysql.gif)

### redis
``` bash
$ go-sniffer [设备名] redis [参数]
-p 置顶端口，默认6379
```
![image](https://github.com/40t/go-sniffer/raw/master/images/redis.gif)

### http
``` bash
$ go-sniffer [设备名] http [参数]
-p 置顶端口，默认80
```
![image](https://github.com/40t/go-sniffer/raw/master/images/http.gif)

### mongodb
``` bash
$ go-sniffer [设备名] mongodb [参数]
-p 端口，默认27017
```
- 支持大部分语句，只有个别少数语句没有实现

## License:
[MIT](http://opensource.org/licenses/MIT)
