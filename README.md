# 日常 

1. rem 
2. 检测设备分像素宽高 像素比 (用于移动端兼容)
3. 使用媒体查询 @media 做兼容适配
4. vue 刷新组件
5. npm  run 报错 
6. meta 标签
7. css  修改占位文字的默认样式 
8. vue 打包后低版本 ios 安卓白屏

### 1. rem 
 1. 在header里写入 (750px设计稿)

    
  ``` 
   document.querySelector('html').style.fontSize=(document.documentElement.clientWidth/750)*100+"px";
  ``` 
  rem 2 s
 ```
 (function(doc,win){
			var docEl = doc.documentElement,resizeEvt = 'orientationchange' in window ? 'orientationchange' : 'resize',
			recalc = function(){
				var clientWidth = docEl.clientWidth;
				if(!clientWidth) return;
				if(clientWidth>=750){
					docEl.style.fontSize = '100px'; //1rem  = 100px
				}
				else{
					docEl.style.fontSize = 100 * (clientWidth / 750) + 'px';
				}
			};
			if (!doc.addEventListener) return;
	        win.addEventListener(resizeEvt, recalc, false);
	        doc.addEventListener('DOMContentLoaded', recalc, false);
})(document,window);
 ``` 
 2. 页面元素px单位 / 100 = rem单位;
### 2. 检测设备分像素宽高 像素比 (用于移动端兼容)
   - 检测屏幕像素宽度  ---  window.screen.width;
   -  检测屏幕像素高度  --- window.screen.height;
   -  检测屏幕像素比    ---   window.devicePixelRatio;

### 3. 使用媒体查询 @media 做兼容适配
```  
 @media only screen and (device-width: 375px) and (device-height: 812px) and (-webkit-device-pixel-ratio: 3) {
     /*这里写具体的样式*/
     }
```



### 4. vue 刷新组件
```
<component v-if="hackReset"></component>
this.hackReset = false
this.$nextTick(() => {
  this.hackReset = true
})

```

### 5. npm  run 报错 

```
npm install 报错
npm install chromedriver --chromedriver_cdnurl=http://cdn.npm.taobao.org/dist/chromedriver
--------------
npm run dev 报错   
npm install node-sass


```

### 6. meta 标签

```
<meta content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=0;" name="viewport"/>

/*强制让文档的宽度与设备的宽度保持1:1，并且文档最大的宽度比例是1.0，且不允许用户点击屏幕放大浏览；user-scalable: 用户是否可以手动缩放*/

<meta content="yes"name="apple-mobile-web-app-capable"/> 
/*iphone设备中的safari私有meta标签，它表示：允许全屏模式浏览；*/

<meta content="black"name="apple-mobile-web-app-status-bar-style"/>
/*iphone的私有标签，它指定的iphone中safari顶端的状态条的样式；*/

<meta content="telephone=no"name="format-detection"/>
/*忽略将页面中的数字识别为电话号码*/

<meta content="email=no"name="format-detection"/>
/*忽略将页面中邮件地址*/
```

### 7. css  修改占位文字的默认样式 

```
input::-moz-placeholder, textarea::-moz-placeholder {
    color: #cccccc;
} 
input:-ms-input-placeholder, textarea:-ms-input-placeholder { 
    color: #cccccc;
} 
input::-webkit-input-placeholder, textarea::-webkit-input-placeholder {
    color: #cccccc;
}

```
### 8. vue 打包后低版本 ios 安卓白屏

```
/* es6转es5 */

1.npm install --save-dev babel-preset-es2015（安装ES2015转码规则）

2.npm install --save-dev babel-polyfill

3.npm install es6-promise

4.main.js 中引用 

import Es6Promise from 'es6-promise'

Es6Promise.polyfill()

import 'babel-polyfill'

5.修改.babelrc文件  

{
  "presets": ["es2015" , "stage-2"],
  "plugins": ["transform-vue-jsx", "transform-runtime"]
}

6.webpack.base.conf.js 中修改
  对VUX进行转ES5
   {
    test: /vux.src.*?js$/,
    loader: 'babel-loader',
    query: { presets: ['es2015'] },
   },
 对自定义脚本进行转ES5
    {
      test: /\.js$/,
      loader: 'babel-loader',
      query: { presets: ['es2015'] },
      include: [resolve('src'), resolve('test'), resolve('node_modules/webpack-dev-server/client')]
    }

```


#### Mail : 211366323@qq.com
