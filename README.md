# WxyHttpsWorking
基于AFN3.1.0的https SSL认证

近来关于苹果对https审核相关的信息在iOS开发者中讨论很多，恰巧由于工作原因之前已经进行过关于https的相关设置，所以便整理了一下。

首先web服务器必须提供一个ssl证书，需要一个 .crt 文件，然后设置app只能连接有效ssl证书的服务器。

在开始写代码前，先要把 .crt 文件转成 .cer 文件，然后在加到xcode 里面

###  .crt 文件转成 .cer 文件

* 打开电脑终端，使用openssl进行转换:
 ` openssl x509 -in 你的证书.crt -out 你的证书.cer -outform der
`
* 通过安装crt文件，电脑导出：

   1）先打开“钥匙串访问”

   2）选中你安装的crt文件证书，选择“文件”--》“导出项目”
   
   3）选择.cer证书，存储即可。

### 将转成的.cer文件拖入工程，将Demo中的“WxyNetWorking”文件夹拖入工程，在网络请求的类中引入头文件“WxyNetWorking.h” 就可以正常的网络请求了。相信你一定会网络请求。



###### 注：由于cer证书是真实的项目在用，不便提供，因为没有找到合适的请求链接所以Demo中没有演示，敬请谅解。


## 相关阅读
[ATS配置官方说明 (官方文档第一)](https://developer.apple.com/library/content/documentation/General/Reference/InfoPlistKeyReference/Articles/CocoaKeys.html#//apple_ref/doc/uid/TP40009251-SW33)

[《HTTPS权威指南》- SSL、TLS和密码学学习笔记](https://gold.xitu.io/post/5856b15dac502e0067ef48cc)

[《HTTPS权威指南》-协议学习笔记](https://gold.xitu.io/post/5857f7d9ac502e0067008044?utm_source=gold_browser_extension)

[《HTTPS权威指南》-公钥基础设施（PKI）学习笔记](https://gold.xitu.io/post/5859ed8c8e450a006c85529f?utm_source=gold_browser_extension)

[苹果强制使用HTTPS传输后APP开发者必须知道的事](http://wetest.qq.com/lab/view/274.html)


## 许可证
WxyHttpsWorking 使用 MIT 许可证，详情见 LICENSE 文件。

  