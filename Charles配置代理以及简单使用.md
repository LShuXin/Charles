# Charles配置代理以及简单使用

## 一、简介
### 1、概念

![请添加图片描述](1b11d944932d459eb5185684be20c90c.png)charles中文名叫青花瓷，它是一款基于HTTP协议的代理服务器，通过成为电脑或者浏览器的代理，然后截取请求和请求结果达到分析抓包的目的。
**特点：**跨平台、半免费。

半免费：

```
启动等到10S。

半个小时重启一次。
```

### 2、工作原理

![请添加图片描述](f499ec3f69814c788dcb55c76a800515.png)

前置步骤：

```
需要运行Charles并配置代理
在客户端上面需要配置代理
```

步骤：

```
由客户端发送请求
Charles接收再发送给服务端
服务端返回请求结果给Charles
由Charles转发给客户端
```

### 3、主要功能

```
支持Http和Https代理
支持流量控制
支持接口并发请求
支持重发网络请求
支持断点调试
```

### 4、优点

![请添加图片描述](149c9fa9a6664c72be5ad0f37dfab9b3.png)

### 5、Charles组件介绍

![请添加图片描述](d60404c375294cf681327e3257b613ad.png)

![请添加图片描述](f2932cadc942429baca1ca654ced08a2.png)

![请添加图片描述](https://img-blog.csdnimg.cn/5be5da28b7744b4aa2635bf170c6c17f.png)

## 二、初始化安装(MacOS)
### 1、Charles安装
[官网](https://www.charlesproxy.com/)

![请添加图片描述](6f89669f74624848afae685858f8661f.png)

### 2、配置代理(获取Http)

#### 2.1 代理设置

![请添加图片描述](9bd929e22fb34dd7b17f1528e18c9890.png)

#### 2.2 获取本机IP

![请添加图片描述](7ceffbf7b7484eefab72ef3064c6050e.png)

#### 2.4 访问控制
限定IP进行访问

![请添加图片描述](6702fcdcd15d41ed8fa049a648c1b478.png)

#### 2.5 设置Mac电脑代理

![请添加图片描述](005cd7365bca4f7dbc6d83b8bee8aebc.png)



#### 2.6 http校验

[Http校验](http://ihrm-test.itheima.net/#/login)

### 3、配置Https

#### 3.1 安装SSL证书

安装证书：

![请添加图片描述](56563be4fb684c20907806457aace38a.png)

授权证书：

![请添加图片描述](f1efe3ae5fbf4ef9aff0a1488f1707bc.png)

结果验证：

![请添加图片描述](76f4ec012c2e4459adc289901ae0c640.png)

#### 3.2 配置SSL代理

![请添加图片描述](01c0e118edc645fdba93d8d275ee8ad2.png)

#### 3.3 结果验证

请求百度网页后，能在Charles中看到请求信息和返回信息既可。

![请添加图片描述](bd0c13d2f8874b5bb09c48d3758cefcb.png)

## 三、Charles使用
### 1、流量配置
```
在Charles窗口中点击菜单 “Proxy”-> “Throttle Setting”
在打开的设置窗口中勾选 “Enable Throttling”
在“Throttle preset”下拉框中选择对应的网络类型
点击 “oK”
```

![在这里插入图片描述](051a0f65e6d142e4ba450d9cb9ada847.png)

![在这里插入图片描述](d8836022ab854f60bf57f26ed89767b9.png)

![在这里插入图片描述](515207d284634356b4b28e37c72e777f.png)

### 2、断点配置

```
右击接口链接，选择 “Breakpoints”
在浏览器刷新对应接口的页面
此时会自动跳转到Charles并显示出接口请求信息
点击“Edit Request”，修改请求的信息，点击 “Execute”
点击 “Edit Response”
在数据格式栏中选择合适的显示格式，比如 “ Json”
修改对应的数据，点击 “Execute”
回到浏览器查看数据应该为修改之后的Response的信息
```



### 3、断点调试
```
右击接口链接，选择 “Breakpoints”
在浏览器刷新对应接口的页面
此时会自动跳转到Charles并显示出接口请求信息
点击 “Edit Request”，修改请求的信息，点击“Execute"
点击 “Edit Response”
在数据格式栏中选择合适的显示格式，比如 “Json”
修改对应的数据，点击 “Execute”
回到浏览器查看数据应该为修改之后的Response的信息
```



![在这里插入图片描述](720af25c6af84f778003534b62b5fc9f.png)

编辑请求参数：

![在这里插入图片描述](611b6fa5af644a44bace38ffe068a63e.png)




## 四、Windows客户端配置
### 1、Windows代理配置

```
在chrome浏览器中输入Chrome://setting
在搜索框中输入“代理”
点击“打开您计算机的代理设置”
在手动设置代理中 开启代理
在地址输入框中输入Charles的1P地址以及端口
点击“保存”，关闭页面。
```

![在这里插入图片描述](4f2eaa5b644547f28f4d0f8d49ca9b4e.png)

![在这里插入图片描述](3245d12d90a746c3843d306af79abe95.png)

### 2、Window中Https配置
```
打开charles，选择“help”—>“SSL Proxying“—>“Install Charles Root Certificate“
在打开的证书框中，点击“安装证书”，选择“本地计算机”，点击“下一步“
选择“将所有证书都存放下列存储”，再点击“浏览”
选择“受信任的根证书颁发机构”，点击“确定”—>“下一步”—>“完成”
```

![在这里插入图片描述](ea9134d851c046cf93b615e16f156f70.png)

![在这里插入图片描述](32c7bd54b5544c66bb601ddf429f5e26.png)