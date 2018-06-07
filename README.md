#大王的笔记-移动端
# 自适应布局  rem 
 1. 在header里写入 
    
  ```  document.querySelector('html').style.fontSize=(document.documentElement.clientWidth/750)*100+"px";
  ``` 
# 检测设备分像素宽高 像素比 (用于移动端兼容)
   > *  检测屏幕像素宽度  ---  window.screen.width;
   > *  检测屏幕像素高度  --- window.screen.height;
   > *  检测屏幕像素比    ---   window.devicePixelRatio;

# 使用媒体查询 @media 做兼容适配
```  
 @media only screen and (device-width: 375px) and (device-height: 812px) and (-webkit-device-pixel-ratio: 3) {
     /*这里写具体的样式*/
     }

```

#### → 211366323@qq.com