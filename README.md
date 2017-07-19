# LomoX 2 -- Learn LomoX 

### 当前Demo
* lomox-01-hello-react 

### 支持的操作系统
Win7以上系统，原因QT5.9已经不支持XP了。

### 如何调试
js调试请不要按F12打开调试器（会挂的，后期会屏蔽F12按键）   
调试请打开程序后，通过Chrome访问http://localhost:9000/ 来调试   

### 注意事项 
当前非最终完善版，所以有一些bug正常。  
注意看 Resources\js\stdlib下LxExt-1.0.dev.js。
WebEngine改用QWebChannel与C++进行交互，而且需用回调如下所示。 
 
	var thechannel = new QWebChannel(qt.webChannelTransport, function(channel) {
        window.LxDialog = channel.objects.LxDialog;
		window.LomoX = channel.objects.LomoX;//设置js全局对象
	);
	LomoX.getVersion(function(returnValue) {   //使用js对象
		console.log(returnValue);  
		}); 
	}
	
如用自己写的面页必须在html文件中加入

	<script type="text/javascript" src="qrc:///qtwebchannel/qwebchannel.js"></script> 
	
参考Resources\index.html（后期会尝试在代码层加入）。
	

### 官方联系方式
QQ群: 41830909  (LomoX-WebUI)


