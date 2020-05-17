## 使用Golang 自建 VPN

`<第一步>` :购买一台海外的服务器 
<br>
aws , aliyun .....

`<第二步>` :登录服务器安装golang 环境
<br>
<https://www.jianshu.com/p/33cf4f41cae9> 自己baidu...

`<第三步>` :安装shadowsocks2 代理 & 配置账号
<br>

<https://github.com/shadowsocks/shadowsocks-go>

<https://github.com/shadowsocks/go-shadowsocks2>

shadowsocks 和 shadowsocks2 支持的加密方式不一样,
如果你使用的客户端不支持DUMMY,CHACHA20-IETF-POLY1305,AES-128-GCM,,AES-256-GCM 那就不要安装 shadowsocks2。
ShadowsocksX-NG 是支持的


按照github.com/shadowsocks/go-shadowsocks2操作

到可执行文件 go-shadowsocks2 执行
go-shadowsocks2 -s 'ss://AEAD_CHACHA20_POLY1305:your-password@:8488' -verbose 启动服务

本地telnet ip 8488 , 如果通查看



`<第四步>` :安装客户端代理,  (如果安装了其他也ok)
<br>
<https://github.com/shadowsocks/ShadowsocksX-NG>

`<第五步>` :配置Client VPN账号
<br>
配置完成后->https://www.google.com/


`<第六步>` :安装Serverspeeder(TCP加速引擎) 
如果 https://www.google.com/ 很慢可以自行安装











