### grunt angular项目sass报错
* sass模块报错
	* 重装sass
		* gem install sass
		* sass -v查看是否安装成功
		* 权限问题：sudo gem install sass
	* 重装ruby
		* 使用homebrew获得ruby：brew install ruby


### &lt;input type="number"&gt;maxlength失效
* 移动端页面为了方便用户交互通常将手机号输入框和数字输入框设置type属性，在用户触发fcous（）时手机键盘自动弹出数字键盘。
* 解决方案：修改为&lt;input
type="tel"&gt;可以起到同样的效果

### npm包缺失报错
* 删除项目中的node_modules 并尝试重新 npm install,如重新安装之后还是报相同错误，请尝试下面的做法
* 删除本地项目node_modules包，复制相同项目相同操作系统的依赖包
* 指定依赖和版本安装
	* 如：缺少webpack-merge包,首先查看是否安装了webpack-merge模块`npm ls --depth=0` 

	* 如果没有重新安装指定依赖和版本
`npm install webpack-merge --save-dev`

### swiper滑动失效
* 使用swiper会碰到模块滑动失败的问题，这种问题在vue、angular这种框架下发生几率高，原因在于模块数据未加载完成就开始初始化swiper导致
* 解决方案：
	* 一：使用settimeout()进行延时，不易过长，300毫秒足够，但是要注意的是js的作用域问题
	* 二：使用swiper自带的属性进行自动初始化
	
```
swiper1 = new Swiper('.swiper-container', {  
    initialSlide :0,  
    observer:true,//修改swiper自己或子元素时，自动初始化swiper  
    observeParents:true//修改swiper的父元素时，自动初始化swiper  
});  
```
* 个人建议使用第一种，两种结合来用也可以，第一种方案可以完美解决失效问题。