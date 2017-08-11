![rocket](https://github.com/moumoonyuka/hosts-for-proxy/blob/master/7390867116.gif)
  
 #<center> 小火箭科学上网</center>  

`配置文件` 

----------

* ***hosts_SR.conf***
    
      未屏蔽广告

* ***hosts_SR_Adb.conf***
    
      屏蔽广告（优酷，爱奇艺，网页广告等）

* ***hosts_Android_20170811.conf***
    
      最新安卓，苹果，Windows通用hosts配置文件
----------
`配置文件基本语法`


``` javascript
//基于域名判断并屏蔽（REJECT）请求
DOMAIN,pingma.qq.com,REJECT
*
// 基于域名后缀判断屏蔽（REJECT）请求
DOMAIN-SUFFIX,flurry.com,REJECT
*
// 基于关键词后缀判断走代理（Proxy），强制不尊重系统代理的请求走
Packet-Tunnel-Provider DOMAIN-KEYWORD,google,Proxy,force-remote-dns
*
// 基于域名后缀判断请求走直连（DIRECT）
DOMAIN-SUFFIX,126.net,DIRECT
*
// Telegram.app 指定“no-resolve”Surge 忽略这个规则与域的请求。
IP-CIDR,91.108.56.0/22,Proxy,no-resolve
*
// 判断是否是局域网，如果是，走直连
IP-CIDR,192.168.0.0/16,DIRECT
*
// 判断服务器所在地，如果是国内，走直连
GEOIP,CN,DIRECT
*
// 其他的全部走代理
FINAL,Proxy
*
// 其他的全部不走代理
FINAL,DIRECT
```
----------
