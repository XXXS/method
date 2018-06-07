# 移动端
## 1. rem 
 1. 在header里写入 (750px设计稿)
    
  ``` 
   document.querySelector('html').style.fontSize=(document.documentElement.clientWidth/750)*100+"px";
  ``` 
 2. 页面元素px单位 / 100 = rem单位;
## 2. 检测设备分像素宽高 像素比 (用于移动端兼容)
   - 检测屏幕像素宽度  ---  window.screen.width;
   -  检测屏幕像素高度  --- window.screen.height;
   -  检测屏幕像素比    ---   window.devicePixelRatio;

## 3. 使用媒体查询 @media 做兼容适配
```  
 @media only screen and (device-width: 375px) and (device-height: 812px) and (-webkit-device-pixel-ratio: 3) {
     /*这里写具体的样式*/
     }
```

#### Mail : 211366323@qq.com