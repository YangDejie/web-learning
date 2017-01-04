<h1>第**4**章 多媒体与**Web**设计 </h1>

# 1 多媒体Web设计原则★

- 多媒体技术不是各种信息媒体的简单组合，它是一种把[文本](http://baike.baidu.com/view/300107.htm)、[图形](http://baike.baidu.com/view/42121.htm)、[图像](http://baike.baidu.com/view/42116.htm)、[动画](http://baike.baidu.com/view/7262.htm)和[声音](http://baike.baidu.com/view/27063.htm)等形式的信息结合在一起，并通过[计算机](http://baike.baidu.com/view/3314.htm)进行综合处理和控制，能支持完成一系列交互式操作的[信息技术](http://baike.baidu.com/view/3226.htm)。
- 特性：交互性和非线性。 

网站使用多媒体应遵守的一般设计原则：

- ①根据网站主题选择多媒体
- ②重视网络带宽，慎用视频
- ③网页应避免使用背景音频
- ④避免网页使用零乱的动画
- ⑤网页中避免使用滚动文本
- ⑥网站中避免使用特别插件


- - 例如Flash，Media Player，QuickTime、RealPlay和Shockwave插件等。


- ⑦网站拒绝最新最耀眼技术。
- ⑧避免网站设计的版权侵害
- **珍惜Web用户时间-时刻吸引用户**

# 2 动画与Web设计★

- Web动画从简单的动画GIF图像到3D动画以及虚拟环境 

- 合理使用动画可以达到事半功倍的效果 

- 在设计中切不可滥用 

- 动画：利用人的视觉暂留特性，快速播放一系列连续运动变化的图形图像，也包括画面的缩放、旋转、变换、淡入淡出等特殊效果。

- 动画是由一系列静态画面连续地播放形成的，每个动画页面称为帧(Frame)，一秒钟动画所包含的帧数称为帧速率(fps)，计算机上的动画一般达到15fps时，播放就已经很流畅了。(DVD帧速率：30fps；电影帧速率：24fps)

- 最常使用的基本动画类型

  - 1)  SVG 动画
  - 2)  GIF 动画


- - 有多幅静态GIF图片组合而成，
    - 它制作简单，并得到了浏览器的广泛支持。其原理类似于播放幻灯片。
    - 动画GIF一般用于条幅广告、口号或同一类多幅图片的展示。
    - 但是它的缺点同样突出：没有声音，不能停止播放。
    - GIF 动画的制作工具有Photoshop，Ulead GIF Animator和GIF Movie Gear等。

- 3)   JavaScript 或VBScript 创建动画


- - 可以使用DOM+CSS改变元素的外观，而通过每隔一段时间调用一次改变元素外观的函数，实现类似Flash的渐类动画
    - ​
    - 翻转动画(Rollovers)


- - - 翻转动画主要用于按扭、图像或者网页上的其他指定区域
      - 当用户鼠标滑过时触发动作，
      - 翻转动画通常用于导航元素，它们给用户创建交互事件，也可以是一个超级链接。


- ​

- - JS库


- - - JQUERY

        - - **JavaScript**和查询（**Query**），
          - 辅助**JavaScript**开发的库。
          - **jQuery**是免费、开源的，使用[**MIT**](http://baike.baidu.com/subview/74918/8382747.htm)许可协议。
          - **jQuery**的语法设计可以使开发更加便捷，


        - - - 例如操作[文档](http://baike.baidu.com/view/55621.htm)对象、选择[**DOM**](http://baike.baidu.com/view/14806.htm)元素、制作动画效果、事件处理、使用[**Ajax**](http://baike.baidu.com/view/1641.htm)以及其他功能。


        - - **jQuery**提供**API**让开发者编写插件。
          - ​
          - 动画一般，：布局颠簸**“ **过分忙于布局处理工作
    
      - 动画库velocity.Js


- - 4)   Flash动画


- - - Flash功能强大并且被很多网站使用
      - 需要下载Flash插件。
      - Adobe Flash现在已是Web动画的事实工业标准，因此Web Flash动画应采用Adobe Flash。2005年Adobe公司并购了Mediamedia公司，Adobe Flash CS3 Professional 是Macromedia Flash的后继产品。


- - 5)   css


- - - CSS3，能够创建动画，这可以在许多网页中取代动画图片、Flash 动画以及 JavaScript
      - @keyframes 规则用于创建动画。
      - 在 @keyframes 中规定某项 CSS 样式，就能创建由当前样式逐渐改为新样式的动画效果。


- - - - Internet Explorer 10、Firefox 以及 Opera 支持 @keyframes 规则和 animation 属性。
        - Chrome 和 Safari 需要前缀 -webkit-。

    - 常见的动画设计效果主要有：

    - - ①条幅信息循环水平滚动播出
        - ②新闻通知等标示图标色彩图案交替显示(跳动与闪动)
        - ③纵向滚动新闻通知的标题超链接信息
        - ④沿某一定轨迹运动的悬浮通知
        - ⑤多幅新闻照片或风光照片的循环切换
        - ⑥某些元素的色彩循环动画
        - ⑦元素的缓慢旋转，旋转结束标示网页或图片等下载完成
        - ⑧元素的闪烁、淡入、淡出、爆炸与组合
        - ⑨图像之间的过渡与变形
        - ⑩子导航的弹出以及与主题相关的Flash动画





# 3 视频与Web设计 ★

- Web视频一般分辨率低、像素少、帧速率低、尺寸小 
- 自动播放 / 用户启动
- - - `<EMBED SRC=“ducks.avi width=145 height=60>`

- 点击播放


- - `<A HREF = “ducks.avi> 1.5 MB AVI Video </A>`


- **1)  **使用 `embed`标签


- - `<embed>` 标签的作用是在 HTML 页面中嵌入多媒体元素。
  - `<embed src="movie.swf" height="200" width="200"/>`
  - http://www.w3school.com.cn/tiy/t.asp?f=html_video_embed


- **2) **使用`object`标签


- - `<object> `标签的作用是在 HTML 页面中嵌入多媒体元素。
  - `<object data="movie.swf" height="200" width="200"/>`
- 3)使用 `video`标签


- - - `<video> `是 HTML 5 中的新标签。
    - `<video> `标签的作用是在 HTML 页面中嵌入视频元素。
    - 以下 HTML 片段会显示一段嵌入网页的 ogg、mp4 或 webm 格式的视频：

- `<video width="320" height="240“ controls="controls"> `

- `<source src="movie.mp4" type="video/mp4" /> `

- `<source src="movie.ogg" type="video/ogg" /> `

- `<source src="movie.webm" type="video/webm" /> `

- Your browser does not support the video tag. 

- `</video> `

- - 您必须把视频转换为很多不同的格式。
  - `<video>` 元素在老式浏览器中无效。
  - http://www.w3school.com.cn/tiy/t.asp?f=html_video_html5

# 4 音频与Web设计 ★

- Web音频主要有内嵌音频和可下载音频
- ⒈ 内嵌音频


- - 在网页设计中一般是拒绝背景音频的。
  - 内嵌音频一般主要用于视频、Flash动画的伴音
  - `<EMBED SRC = “daisy.wav”> `or 
    `<BGSOUND = “imagine.wav”>`
  - `<object>`
  - Html5  `<SOUND>`


- ⒉ 可下载音频


- - 音频文件完全下载到用户客户端后，使用Windows Media Player或RealOnePlayer等媒体播放器进行播放，用户可以对音频完全控制：回放、暂停、停止、音量 

**多媒体网站设计考虑得主要因素**：

  网站主题 、  客 户 群、  用户感受、  网络带宽、  下载时间 、  浏 览 器 

