# search_box
由于 Ajax (XMLHttpRequest)请求受到同源策略的限制。所以需要将本地网页放到bing搜索域下，采用Fiddler工具。
如果我们请求一个服务器上不存在的文件一般是跳转到一个404页面，但是利用fiddler工具可以实现修改服务器响应的结果，呈现给用户一个自定义的文件——我们只需要拦截服务器的响应并替换成我们自己的页面即可。

* 打开fiddler，在浏览器中请求地址http://api.bing.com/index.html
。由于服务器上不存在文件index.html，所以会返回404错误，fiddler捕获此此响应：
![alt](https://github.com/echo-lu/search_box/blob/master/img/1.png)
* 将此response替换成我们想要放在服务器上的本地文件index.html,选中上一步中的404记录，点开其AutoResponder，勾选如图两个选项，点击add rules;
![alt](https://github.com/echo-lu/search_box/blob/master/img/2.png)
* 接着在Rule Editor中选择自己所要添加的文件，将所有需要的资源都添加上
![alt](https://github.com/echo-lu/search_box/blob/master/img/3.png)
* 刷新页面就可以了：
![alt](https://github.com/echo-lu/search_box/blob/master/img/4.png)

