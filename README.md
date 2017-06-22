# base_mixins
基于sass开发的简写、组合速写的混合宏<br>

### 全局设置参数:
$support-for-ie   : true(默认)/false;  ( 兼容老版ie ) <br>
$vendors          : webkit moz ms o;  ( 设置css3前缀 )<br>
$prefixWebkit     : true!default(默认)/false   ( 开启谷歌前缀 )<br>
$prefixMozilla    : true !default(默认)/false; ( 火狐前缀:moz前缀 )<br>
$prefixMicrosoft  : true!default(默认)/false;  ( IE前缀:ms前缀 )<br>
$prefixOpera      : true!default(默认)/false;  ( opera前缀:o前缀 )<br>
$prefixNo         : false!default(默认)/false; ( 默认 )<br>
$global-unit      : px;  ( 默认补全单位 )<br>
$designWidth      : 640; ( 移动转rem默认尺寸大小 ) <br>
$wxDesignWidth    : 750;    ( 微信小程序转rpx默认尺寸大小 ) <br>

### 动画混合宏(_animation.scss):

keyframes ( @keyframes 规则 )<br>
```
css3动画,只能写在调用页面,配合.css3( @style,@frames )使用    
例子 :                                                                
      @include keyframes(animation-name) {                                                
          0% {                                                             
             #{$browser}transform: translate3d(100%, 0, 0);                
          }                                                                
          100% {                                                           
              #{$browser}transform: translate3d(0%, 0, 0);                 
          }                                                                
       }                                                                    
      .className{ @include css3(animation,animation-name 5s infinite); }
``` 
ani ( animation动画 )<br>
```
例子 :
   .className{ @include ani(keyframes 5s infinite); }    
```
ani-name ( animation动画名称 )<br>
```
例子 :
   .className{ @include ani-name(keyframes-name); }  
```
ani-dur ( animation动画成一个周期所需要的时间 )<br>
```
例子 : (不传参数默认0.2s)
   .className{ @include ani-dur(0.2s); }  
```
ani-time ( animation动画速度形式 )<br>
```
例子 : (不传参数默认linear)
   .className{ @include ani-time(linear); }  
```
ani-itc ( animation动画播放次数 )<br>
```
例子 : (不传参数默认1)
   .className{ @include ani-itc(1); }  
```
ani-dir ( animation动画轮流反向播放动画 )<br>
```
例子 : (不传参数默认alternate)
   .className{ @include ani-dir(alternate); }  
```
ani-play ( animation动画"播放"或"暂停" )<br>
```
例子 : (不传参数默认running)
   .className{ @include ani-play(running); }  
```
ani-del ( animation动画延迟时间设置 )<br>
```
例子 : (不传参数默认0.2s)
   .className{ @include ani-del(0.2s); }  
```
ani-fill ( animation动画运动完成后的状态设置 )<br>
```
例子 : (不传参数默认forwards)
   .className{ @include ani-fill(forwards); }  
```

### 背景图片混合宏(_background.scss):

bg ( 设置背景颜色和图片 )<br>
```
例子 :
   .className{ @include bg(#fff,'../i/a.jpg'); }  
   或
   .className{ @include bg(#fff); }  
```
no-bg ( 取消背景 )<br>
```
例子 :
   .className{ @include no-bg; }   
```
bgi ( 设置图片背景 )<br>
```
例子 :
   .className{ @include bgi('../i/new-close.gif',$position:center center); }  
```
bgz ( 设置background-size )<br/>
```
例子 : (不传参数默认cover)
   .className{ @include bgz(cover); }  
```
bg-clip ( 设置background-clip )<br>
```
例子 : (不传参数默认content-box)
   .className{ @include bg-clip(content-box); }  
```
bgo ( 设置background-origin )<br>
```
例子 : (不传参数默认content-box)
   .className{ @include bgo(content-box); }  
```
bgp ( 设置background-position )<br>
```
例子 : (不传参数默认center center)
   .className{ @include bgp(center center); }  
```
bgc  ( 设置背景颜色 )<br>
```
例子 : 
   参数1 $color:为颜色;
   参数2 $support-for-ie:默认为true 是否兼容rgba兼容ie;
   .className{ @include bgc(#fff); } 
   或者
   .className{ @include bgc(rgba(0,0,0,0.2)); }  
```

### 块混合宏(_block.scss):

block ( 块 )<br>
```
例子 : 
   参数: $args:false(默认) 是否加!important;
   .className{ @include block; } 
   或者
   .className{ @include block(true); }  
```
inline ( inline )<br>
```
例子 : 
   .className{ @include inline; }  
```
inblock ( inline-block )<br>
```
例子 : 
   .className{ @include inblock; }  
```
box ( box )<br>
```
例子 : 
   .className{ @include box; }  
```
table ( table )<br>
```
例子 : 
   .className{ @include table; }  
```
none ( none )<br>
```
例子 : 
   参数: $args:false(默认) 是否加!important;
   .className{ @include none; } 
   或者
   .className{ @include none(true); }  
```
show ( 显示 )<br>
```
例子 : 
   .className{ @include show(); }  
```
hide ( 隐藏 )<br>
```
例子 : 
   .className{ @include hide; }  
```
box-sz ( 怪异盒模型 )<br>
```
例子 :  (不传参数默认border-box)
   .className{ @include box-sz( border-box ); }  
```
box-fx ( 设置元素可伸缩其尺寸 )<br>
```
例子 :  (不传参数默认1)
   .className{ @include box-fx(1); }  
```
box-o ( 设置子元素应该被水平或垂直排列 )<br>
```
例子 :  (不传参数默认horizontal)
   .className{ @include box-o(horizontal); }  
```
horizontal ( 设置子元素水平排列 )<br>
```
例子 : 
   .className{ @include horizontal; }  
```
vertical ( 设置子元素垂直排列 )<br>
```
例子 : 
   .className{ @include vertical; }  
```
box-dir ( 规定框元素的子元素方向排列 )<br>
```
例子 : (不传参数默认reverse)
   .className{ @include box-dir( reverse ); }  
```
reverse  ( 反方向排列 )<br>
```
例子 :
   .className{ @include reverse; }  
```
no-box-dir  ( 默认方向方向排列 )<br>
```
例子 :
   .className{ @include no-box-dir; }  
```

### 浮动混合宏(_clear.scss):

fl  ( 左浮动 )<br>
```
例子 :
   .className{ @include fl; }  
```
fr  ( 右浮动 )<br>
```
例子 :
   .className{ @include fl; }  
```
clear  ( 清浮动 )<br>
```
例子 :
   .className{ @include clear; }  
```

### 文本的混合宏(_text.scss):

tofl  ( 超出一行.... )<br>
```
例子 :
   .className{ @include tofl; }  
```
erow  ( 多行显示... )<br>
```
例子 : (不传参数默认2行)
   .className{ @include erow(2); }  
```
bword  ( 强制折行 )<br>
```
例子 : 
   .className{ @include bword; }  
```
wdw  ( 断行 )<br>
```
例子 : 
   .className{ @include wdw; }  
```
hide-text  ( 隐藏文字 )<br>
```
例子 : (不传参数默认101%)
   .className{ @include hide-text(); }  
```
hide-text  ( text-indent )<br>
```
例子 : (不传参数默认2em)
   .className{ @include ti(2em); }  
```
replace-text  ( text-indent  )<br>
```
例子 : 
   参数1 $image: 图片路径;
   参数2 $x: 图片x轴;
   参数3 $y: 图片y轴;
   .className{ @include replace-text(2em); }  
``` 
tal  ( 文字居左对齐 )<br>
```
例子 :
   .className{ @include tal; }  
```
tar  ( 文字居右对齐 )<br>
```
例子 :
   .className{ @include tar; }  
```
tac  ( 文字居中对齐 )<br>
```
例子 :
   .className{ @include tac; }  
```
line-over ( 上划线 )<br>
```
例子 :
   .className{ @include line-over; }  
```
line-del ( 删除线 )<br>
```
例子 :
   .className{ @include line-del; }  
```
line-underline ( 下划线 )<br>
```
例子 :
   .className{ @include line-underline; }  
```
line-blink ( 闪烁 )<br>
```
例子 :
   .className{ @include line-blink; }  
```
no-line ( 取消下划线 )<br>
```
例子 :
   .className{ @include no-line; }  
```

### 设置宽高的混合宏(_size.scss):

w ( 设置width )<br>
```
例子 :
   .className{ @include w(12); }  
```
h ( 设置height )<br>
```
例子 :
   .className{ @include h(12); }  
```
size ( 设置width/height )<br>
```
例子 :
    参数1 width
    参数2 height (可不写,width等于height值) 
   .className{ @include wh(12,30); }
   或者
   .className{ @include wh(12); }  
```


