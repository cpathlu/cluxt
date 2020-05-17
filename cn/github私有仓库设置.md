## 将 github 设为私有仓库


`<第一步>` : 生成token 「如果不是项目的构建者，问项目负责人获取」
<br>
<https://github.com/settings/tokens/new>


`<第二步>` : token 设置到请求头中

```
git config --global http.extraheader "PRIVATE-TOKEN:YOUR_PRIVATE_TOKEN"
```

`<第三步>` : 配置git将请求从ssh转换为http

```
#全局替换拉取域下的所有包
 
git config --global url."git@github.com:xxxx".insteadOf "https://github.com/xxxx"

```

```
#全局替换拉取域下的单个包，使用“全局替换拉取域下的所有包” 可以不设置
git config --global url."git@github.com:xxx/xxxxxxx.git".insteadOf "https://github.com/xxx/xxxxxxx.git"

```


`<第四步>` : 指定域名为私有仓库
```
go env -w GOPRIVATE=github.com
```


`<第五步>` : 检查配置

执行 cat ~/.gitconfig
```
[http]
	extraheader = PRIVATE-TOKEN:xxxxx

[url "git@github.com:xxxxx"]
	insteadOf = https://github.com/xxxx
```

执行 go env

```
GOPRIVATE="github.com"
```

确认配置成功



`<第六步>` : 测试配置结果
```
执行
go mod tidy        


显示
go: finding module for package github.com/xxx
go: found github.com/xx/xxx/inits in github.com/xxx/xxx v1.0.1

恭喜你设置成功啦～
```


### 借鉴
<https://golang.org/doc/faq#git_https>
<br>
<https://segmentfault.com/a/1190000021127791?utm_source=tag-newest>
<br>
<https://www.jianshu.com/p/ca4404512cf3>
<br>































































































































































