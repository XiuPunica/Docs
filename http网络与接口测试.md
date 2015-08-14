## 网络与接口测试

#### breif
* author：老王 [明心见性，可以为神]
* 因为访问不了google和维基百科，所以下面的词条解释都是百度的


### net_transaction
**在开始说之前，先甩几个高大上的问题来装逼一下：**

* 你知道现在有多少种网络传输协议，它们各自有什么特点？
* 何为http？http的连接过程有哪些？
* 这些过程中有哪些风险？
* 这些风险如何在测试中进行发现和验证？
* 如何让开发提升自己的代码质量从而不被坑？

##### net_type
[网络传输协议](http://baike.baidu.com/link?url=PFaGy4ZgcJpKl-Ks3yF-l7WAejJ1Qw9I6JtZm-Rd_v8GlhB2oENnuEXvvHLcFi4auAMFgMEX3SjoIqi-oEtR8_)有多少种，这个还真的很少有人说的清楚，我们在上网使用的时候，常用的也就以下这几种，所以现在就BB这几个吧。

* [***http:***](http://baike.baidu.com/link?url=DTHG4ZL1CwfwRJGuj7Zn2DpTr_zf4OFQPrQkKlcWkyUPM1m_lecrDzgDSnafSlnaLeBfM7A2JqdHbsQyDNkLtK)
	* `无连接` 限制每次连接只处理一个请求。服务器处理完客户的请求，并收到客户的应答后，即断开连接。
	* `支持客户/服务器模式`
	* `灵活` HTTP允许传输任意类型的数据对象。正在传输的类型由Content-Type加以标记
	* 目前绝大部分的网络传输都使用该协议，也是我们要讨论的重点
	* 使用的端口是`80`

* [***https:***](http://baike.baidu.com/link?url=8hROHr3gEHCd85LIlE5hJ_OHxwazs8glb5LdeZ3FPiRQpzPTxi8iUtc_fW_YBC37vAn4Gn_3nNVTfiYeWN82Oa)
	* 使用`SSL作为应用层`，数据加密
	* 使用的端口是`443`
* [***ftp:***](http://baike.baidu.com/subview/369/6149695.htm)
	* 用于`文件传输`，且未`明文传输`

* [***ssh***](http://baike.baidu.com/link?url=Q6Zhujvrxm2vEoeb6lL6nYEkHQGzqVeRYeQ8wM0wMqlwmXT9K0okVNCXQAmKhCnV-L7OWJKRwIeLQzKN2296JcvY3sOLgHgZIvlKNWnVMjK) 和 [***telnet:***](http://baike.baidu.com/view/44255.htm)
	* 都是用于`远程登录`
	* `telnet,ftp,pop都是明文传输`,`ssh加密且经过压缩后传输`


##### http_and_network

##### http_code
[code](http://baike.baidu.com/link?url=lWvt15teO-wV4tbnKlGqc37L5AP2QQiqtElQOixi8nOXuJ2qR9L8hLq4wVPtUDUZ_p5NP0NNllhouXfsvbKGZa)


##### http_headers
[headers](http://blog.csdn.net/rainysia/article/details/8131174)

##### python_httplib
**一个python脚本告诉你完整的http请求和返回的处理过程**

<!-- lang:python-->

	import  urllib2
	
	class UrlDemo:
		def __init__(self):
			pass
			
		def prepare(self, params):
			pass
			
		def doQuest(self,url, param_str):
			pass
		
		def render(self, resp):
			pass
			
		def url(self, url, params):
			params_str = self.prepare(params)
			resp = self.doQuest(url, params_str)
			self.render(resp)
			

so，看完上面的脚本，你觉得这中间有哪些地方需要测试？哪些地方可以进行优化
### test_base_charles
***工具基本使用***

连接设置
查看请求

请求的过滤

请求转发和自动返回

限制网速


### interface_test
##### interface_test_quote
接口测试的基本元素

##### simple_interface_test
顺序请求/无关请求的测试

##### mutil_interface_test
并发请求/互相关联请求的测试

##### auto_test
接口的自动化

##### perfermance_test
接口的压力测试及结果分析

