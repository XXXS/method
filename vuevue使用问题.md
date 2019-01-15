#    vue使用问题


### 1. flex布局在ios8 乱码
```
  解决方案:
  1. 注释掉下面代码

//  new OptimizeCSSPlugin({
//  cssProcessorOptions: config.build.productionSourceMap
//   ? { safe: true, map: { inline: false } }
//   : { safe: true }
//  }),

2. 对这个的插件的参数进行配置

new OptimizeCSSPlugin({
 cssProcessorOptions: {
   safe: true,
   // 禁用此插件的autoprefixer功能，因为要使通过postcss来使用          
   autoprefixer: false,
   discardComments: {
      removeAll: true
    }
 },
 canPrint: true
}）


```
