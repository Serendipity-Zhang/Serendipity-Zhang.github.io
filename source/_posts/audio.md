
#   HTML的audio标签



```html
<audio controls>
  <source src="sound.ogg" type="audio/ogg"/>
  <source src="sound.mp3" type="audio/mp3"/>
  Your browser does not support the audio tag.
</audio>
```

## 属性
controls
这是一个boolean值，用于指定是否显示音频控件(即开始/暂停按钮，滚动，音量)

```html
<audio controls></audio>
//or
<audio controls="true"></audio>
```

autoplay
这是个boolean 属性，在页面加载后会自动播放音频文件

```html
<audio aotuplay></audio>
//or
<audio aotupaly="true"></audio>

```


```txt
由于chrome的自动播放政策更改，此功能无法使用
```

muted
这是一个boolean属性,用于指定音频是否开始是会静音，默认为false或为静音

```html
<audio muted></aduio>
 //or
 <audio muted="true"></audio>
```
loop
这是一个boolean属性，用于指定音频文件在播放完之后是否从头开始连续重复播放

```html
<auido loop></audio>
//or
<audio loop="true></audio>

```

preload
此属性用于指定加载页面时音频应该如何加载。这是你与浏览器沟通的方式，不管它是否应该下载和缓存音频文件

```html
<audio preload="none></audio>
```

当页面加载时，浏览器不应该加载音频。如果您希望最小化不必要的流量，并且不希望用户立即使用媒体资源，那么它将非常有用。

```html
<audio preload="metadata"></audio>

```

浏览器应该只在页面加载时加载元数据。同样，当用户不需要立即使用媒体资源时使用。你可以获取的元数据可能包括音频长度，曲目列表，尺寸等等

```html
<audio preload="auto"><audio>
```

当页面加载时，浏览器应该加载整个音频。注意:在某些情况下，这个属性可能会被忽略。当预加载存在时)。

## 单一音源
通过src属性设置一个来源

```html
<audio controls src="sound.mp3">
Your browser does not support the audio tag.
</audio>

```

也可以通过source标签 进行操作

```html
<audio>
<source src ="sound.ogg" type="audio/agg"/>
Your browser does not support the audio tag.
</audio>
```

## 多个音源

与mp3文件相比，ogg音频文件具有更好的声音质量和更小的文件大小。 ，并非所有浏览器都支持它。我们可以在音频标签中传递多个源。 因此这样做

```html
<audios controls>
  <source src="sound.ogg" type="audio/agg"/>
  <source src ="sound.mps" type="audio/mpeg"/>
  Your browser does not support the audio tag.
```

它是自上而下的。这就是为什么我们首先列出ogg，并在浏览器不支持音频标签的情况下添加默认文本的原因。


## javascript 音频事件

play 音频开始播放时
pause 音频暂停时
ended 音频完成时

### 基本用法
您可以添加一个事件监听

```javascript
// 1. select our audio tag

document.querySelector('audio‘）
//2.attach our event listener
.addEventListener('play',() =>{
//do someting
})

```

也可以使用事件属性添加事件
```html
<audio onplay="doSometing()"></audio>
```

```javascript
function doSometing(){
//do someting
}

```