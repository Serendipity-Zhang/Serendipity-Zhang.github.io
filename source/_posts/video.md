# HTML video
 ```html
<video controls>
  <source src="video.webm" type="video/webm" />
  <source src="video.mp4" type="video/mp4" />
  <track src="subtitle.vtt" kind="subtitles" />
  Your browser doesn't support HTML5 video.
</video>
 ```
```html
video 定义视频元素
source 定义视频源
track 定义文本轨道
```
```html
	<video src=“vedio.mp4” controls >
	  <p>
	Your browser doesn't support HTML5 video tag.
         Here‘s <a  href=“video.mp4”> a link to the video
	</p>
    </video>`
-------------------------------------------

     <video src="video.mp4" controls>

  <img src="image.png" >
</video>

```

```html
<video src="video.mp4" controls>
  <object type="application/x-shockwave-flash">
    <!-- flash stuff -->
  </object>
</video>
```

## 定义视频源

用 src 属性定义

```html
<video controls>
  <source src="video.mp4" />
</video>
```

#### 使用的好处<source>是您可以添加视频的不同视频类型。并非所有浏览器都支持相同的视频格式。因此，通过传入多种视频文件格式，您可以让您的浏览器确定哪种格式可行

```html
<video controls>
  <source src="video.webm" type="video/webm" />
  <source src="video.ogg" type="video/ogg" />
  <source src="video/mp4" type="video/mp4" />
</video>

```

属性
controls
autoplay
muted
loop
preload

独特属性 poster：此属性允许传递 URL，因此可以下载视频时或按下播放按钮之前显示的图像

```html
<video width="100" height="100"></video>

//设置视频播放器的高度和宽度

```

## 使用 track 标签添加字幕

如果要添加文本音轨，则可以将 track 子元素添加到 video 中。track 标签有 4 个属性。

```html
<track kind="" lable="" src="" srclang=""

```

您可以添加几个文本轨道，您可以在 kind 属性中表示它。

1.subtitles 不同语言的对话
2.captions 视频转录
3.descriptions 视频内容纹理描述可帮助无法观看视频的用户
4.chapters 章节标题在浏览媒体资源时很有用
5.metadata 他由脚本使用，用户看不见

#### scrlang

设置 kind=“subtitles” 时，必须定义 srclang

```html
<track kind="subtuitles" srclang="zh-TW"

```

### src

在此属性中指定.vtt 的文件位置

```html
<track src="subtitles.vtt" />
```

### lable

在此属性中 您可以指定文本轨道的标题

```html
<track lable="English" />

```

### default

如果有多个文本轨道 可以使用 default 的 boolean 属性来识别，如果未指定用户的 首选项，则默认情况下应启动那个轨道

```html
<video>
  <track kind="subtitles" src="english.subtitles.vtt" srclang="en" default />
  <track kind="sublititles" src="chinese-suntuitles.vtt" scrlang="zh-TW" />
</video>
```

## 上传文件时监听多个事件

1.play 视频开始播放时
2.pause 视频暂停时
3.ended 视频播放完毕后

#### 监听视频完成时的事件

```html
<video id="some-video"></video>
```

```javascript

 cosnt videoEL = document.getElementById('some-video');


 videoEL.addEventListener('ended',function(){

 //do something when the video has finished playing

 })


```
```html
<video onended="doSomething()"></video>
```

```javascript
function doSomething() {
  //do something
}

```

或者

```javascript
const videoEl = document.getElementById("some-video");
videoel.onended = function () {
  //do something when the video has finished palying
};
```
