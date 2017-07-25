# 服务器网络测试一键包

是91yun制作的Linux服务器IO测试、带宽测试、下载测试、路由测试、回程路由测试、全国Ping测试、国外Ping测试、UnixBench跑分测试一键测试包。可以一个命令完成服务器全方位的测试，再也不用担心被不良销售商坑了。下面是蜗牛789之前介绍关于Linux服务器性能测试的文章：

如何对VPS进行性能测试及UnixBench跑分工具使用教程https://www.wn789.com/3620.html

Linux系统信息/IO读写/下载速度一键测试脚本bench.sh https://www.wn789.com/6975.html

Linux系统VPS带宽测速脚本 Speedtest Linux测速工具 https://www.wn789.com/6943.html

# 一、完整测试代码
wget -N --no-check-certificate https://raw.githubusercontent.com/wn789/91yuntest/master/test.sh
bash test.sh -i "io,bandwidth,download,traceroute,backtraceroute,allping,gotoping,benchtest" -u

上面代码是完整测试代码。意思是只要运行上面代码就能一键实现服务器IO测试、带宽测试、下载测试、路由测试、回程路由测试、全国Ping测试、国外Ping测试、UnixBench跑分测试。那是不是可以只选择其中几项自己想测试的项目进行测试呢？Linux服务器性能测试一键包作者很贴心，确实可以根据自己需要进行选择。上面代码中"io,bandwidth,download,traceroute,backtraceroute,allping,gotoping,benchtest"指的就是测试项目，所以项目可以根据自己需要进行删减。下面蜗牛介绍下分别指的是什么内容。

1、io——IO测试，通过DD命令来测试服务器的平均IO水平。

2、bandwidth——带宽测试，使用speedtest来测试服务器的上传和下载带宽。

3、download——下载测试，使用wget来测试到世界各地的下载速度，如果服务器带宽小于10M的话谨慎使用。

4、traceroute——路由测试，从国内部分节点到测试服务器的路由线路。

5、backtraceroute——回程路由测试，测试服务器到国内部分节点的回程路由线路。

6、allping——全国Ping测试，全国各地到测试服务器的Ping值。

7、gotoping——国外Ping测试，测试服务器到日韩美欧等地域的ping值。

8、benchtest——UnixBench跑分测试，该测试耗时将近1小时，并会跑满CPU，请谨慎测试。

#二、测试组合推荐

## 1、IO测试、带宽测试、下载测试、全国Ping测试

wget -N --no-check-certificate https://raw.githubusercontent.com/wn789/91yuntest/master/test.sh
bash test.sh -i "io,bandwidth,download,allping" -u
## 2、IO测试、带宽测试、下载测试、全国Ping测试、路由测试、回程路由测试

wget -N --no-check-certificate https://raw.githubusercontent.com/wn789/91yuntest/master/test.sh
bash test.sh -i "io,bandwidth,download,traceroute,backtraceroute,allping" -u
## 3、IO测试、带宽测试、下载测试、全国Ping测试、路由测试、回程路由测试、国外Ping测试

wget -N --no-check-certificate https://raw.githubusercontent.com/91yun/91yuntest/master/test.sh
bash test.sh -i "io,bandwidth,download,traceroute,backtraceroute,allping,gotoping" -u


## 由于unixbench的测试极其耗资源（cpu和io会长时间处于占满状态），有些IDC禁用，会杀进程或者判断滥用。请谨慎测试。
## 另外unixbench的测试也极其耗时间，建议大家在screen下运行。