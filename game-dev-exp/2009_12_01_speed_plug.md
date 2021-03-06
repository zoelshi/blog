# [game-dev] 加速齿轮防治

## 基本原理

hook住 timeGetTime 等时间函数，在函数返回时修改返回值即可。

 * [http://www.pediy.com/bbshtml/BBS4/kanxue494.htm][1]
 * [http://www.chinaitpower.com/A/2001-10-22/2491.html][2]


## 防治加速

齿轮会导致客户端程序运行加快，发包速率过快，如果服务端不做时间限制，在“跑路”等一些行为上，可以达到加速效果。

方法一：

* 服务器简单处理，对于“跑路”行为，测试一下正常情况数据包间隔是多少，比如间隔为 1 sec 左右；再测试下加速情况下间隔是多少。
* 可以简单定一个规则，比如：连续5次“跑路”包间隔小于 1 sec 的，就认为是“加速”。

方法二：

* 前面的方法不太保险。
* 每次客户端发送“跑路”包，应该带上客户端的时间戳，服务器效验“客户端自己报告的间隔”和“服务器计算的间隔”是否差异过大。过大，则一定是有问题。

[1]:http://www.pediy.com/bbshtml/BBS4/kanxue494.htm
[2]:http://www.chinaitpower.com/A/2001-10-22/2491.html
