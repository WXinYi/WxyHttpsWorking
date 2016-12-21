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



### 注：由于cer证书是真实的项目在用，不便提供，因为没有找到合适的请求链接所以Demo中没有演示，敬请谅解。


## 许可证
WxyHttpsWorking 使用 MIT 许可证，详情见 LICENSE 文件。

  