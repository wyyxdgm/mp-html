# 🔨 属性 :id=prop

!> 需要将某个属性设置为 *false* 时，应写作 *attr="{{false}}"*  

## content
功能：用于渲染的 *html* 字符串  
类型：*String*  

## copy-link
功能：是否允许外部链接被点击时自动复制  
类型：*Boolean*  
默认值：*true*  

?> 对于 *uni-app* 的 *h5* 和 *app* 平台，外链是能够直接跳转的，这种情况下如果该属性为 *true* 则直接跳转外链（而不是复制链接），为 *false* 则不跳转  

## domain
功能：主域名（用于链接拼接）  
类型：*String*  
示例：  
```html
<!-- 假设 domain 属性被设置为 https://example.com
     以下链接均会被拼接为 https://example.com/path -->
<img src="//example.com/path" />
<img src="/path" />
<div style="background-image:url('path')"></div>
```

?> 通过 *base* 标签也可以设置主域名，但优先级低于此属性  

!> 该属性必须填写 协议名://域名 的完整链接  
暂不支持拼接含有 *../* 的相对路径链接  
*a* 标签的 *href* 属性可能需要跳转到小程序内路径，因此不进行 *domain* 拼接  

## error-img
功能：图片出错时的占位图链接  
类型：*String*  

!> 该属性不会进行拼接 [domain](#domain)，需传入完整路径（可以使用本地路径）  

## lazy-load
功能：是否开启图片懒加载  
类型：*Boolean*  
默认值：*false*  

?> 不同平台懒加载的时机不同，具体参考各平台 *image* 组件懒加载的时机  

## loading-img
功能：图片加载过程中的占位图链接  
类型：*String*  

!> 该属性不会进行拼接 [domain](#domain)，需传入完整路径（可以使用本地路径）  

## pause-video
功能：是否在播放一个视频时自动暂停其他视频  
类型：*Boolean*  
默认值：*true*  

?> 如果需要多个视频同时播放的，请将此属性设置为 *false*  

## preview-img
功能：是否允许图片被点击时自动预览  
类型：*Boolean*  
默认值：*true*  

?> 自动预览允许左右滑动查看所有图片，如果不希望如此可以禁用自动预览并在 [imgtap](basic/event#imgtap) 事件中自行处理  

## scroll-table
功能：是否给每个表格添加一个滚动层使其能单独横向滚动  
类型：*Boolean*  
默认值：*false*  

!> 如果表格设置了 *inline* 布局，该属性将不会生效以免破坏行内布局  

## selectable
功能：是否开启文本长按复制  
类型：*Boolean*  
默认值：*false*  

!> 微信 *ios* 端该属性可能失效  

## set-title
功能：是否将 *title* 标签的内容设置到页面标题  
类型：*Boolean*  
默认值：*true*  

## show-img-menu
功能：是否允许图片被长按时显示菜单  
类型：*Boolean*  
默认值：*true*  

!> 该属性目前仅微信、百度和 *uni-app* 的 *app* 平台有效  

## tag-style
功能：设置标签的默认样式  
类型：*Object*  
示例：  
```javascript
// 格式为 标签名: 样式
{
  a: 'color:red' // a 标签默认为红色
}
```

!> 该属性的原理是解析到各标签的内联 *style* 属性中去，如果对特别常用的标签设置默认样式，将大大加大解析结果大小，减慢渲染速度  

## use-anchor
功能：是否使用锚点链接  
类型：*Boolean* / *Number*  
默认值：*false*  

?> 传入一个数字时表示跳转锚点的偏移量（单位 *px*）  

?> 开启该属性会将所有设置了 *id* 属性的标签都暴露出来，一定程度上减慢渲染速度，非必要不要开启  