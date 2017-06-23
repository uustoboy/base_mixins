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

### px转rem的混合宏(_rem.scss);
px2rem ( px转rem )<br>
```
例子 :
    参数1 $px : 转换数字,px单位可不写
    参数2 $important : false(默认)/true 是否加!important
    $designWidth : 640;   
    .className{ @include w(px2rem(100)); }
    或
    .className{ @include w(px2rem(100,true)); }
```
gpx2rem ( 简单rem多值转行 )<br>
```
例子 :
   .className{ @include pal(12,12,12,12); }  
```
px2rpx ( 微信小程序rpx单位函数 )<br>
```
例子 :
   .className{ width : px2rem(100); }
   或
   .className{ @include w(px2rpx(100,true)); } 
```
gpx2rpx ( 简单rpx多值转行 )<br>
```
例子 :
   .className{ @include pal(gpx2rpx(10,10,10,10)); }  
```

### 定位的混合宏(_position.scss);

position ( 定位 )<br>
```
例子 :
   参数1 $position : position的属性;
   参数2 $args :  json 可传(t:0,l:0,b:0,r:0,w:10,h:10,z:10)几个值 
   .className{ @include position(absolute,(t:10px,l:0px,z:5)); }  
```
abs ( 绝对定位 )<br>
```
例子 :
   参数 $args :  json 可传(t:0,l:0,b:0,r:0,w:10,h:10,z:10)几个值 
   .className{ @include position(absolute,(t:10px,l:0px,z:5)); }  
```
rel ( 相对定位 )<br>
```
例子 :
   参数 $args :  json 可传(t:0,l:0,b:0,r:0,w:10,h:10,z:10)几个值 
   .className{ @include position(absolute,(t:10px,l:0px,z:5)); }  
```
fixed ( 固定定位 )<br>
```
例子 :
   参数 $args :  json 可传(t:0,l:0,b:0,r:0,w:10,h:10,z:10)几个值 
   .className{ @include position(absolute,(t:10px,l:0px,z:5)); }  
```
t ( 定位top值 )<br>
```
例子 :
   可不传参数单位 
   .className{ @include t(10); }  
```
l ( 定位left值 )<br>
```
例子 :
   可不传参数单位 
   .className{ @include l(10); }  
```
b ( 定位bottom值 )<br>
```
例子 :
   可不传参数单位 
   .className{ @include b(10); }  
```
r ( 定位right值 )<br>
```
例子 :
   可不传参数单位 
   .className{ @include r(10); }  
```
tl ( 定位top/left值 )<br>
```
例子 :
   参数1 $top : top值;
   参数2 $left : left值;
   参数3 $zindex : z-index值;
   .className{ @include tl(10,10,10); }
   或
   .className{ @include tl(10,10,10); }  
```
rl ( 定位right/left值 )<br>
```
例子 :
   参数1 $right : right值;
   参数2 $left : left值;
   参数3 $zindex : z-index值;
   .className{ @include rl(10,10,10); }
   或
   .className{ @include rl(10,10,10); }  
```
bl ( 定位bottom/left值 )<br>
```
例子 :
   参数1 $bottom : bottom值;
   参数2 $left : left值;
   参数3 $zindex : z-index值;
   .className{ @include bl(10,10,10); }
   或
   .className{ @include bl(10,10,10); }  
```
br ( 定位bottom/right值 )<br>
```
例子 :
   参数1 $bottom : bottom值;
   参数2 $right : left值;
   参数3 $zindex : z-index值;
   .className{ @include br(10,10,10); }
   或
   .className{ @include br(10,10,10); }  
```
trbl ( 定位top/left/bottom/right值 )<br>
```
例子 :
   参数1 $top : top值;
   参数2 $right : right值;
   参数3 $bottom : bottom值;
   参数4 $left : left值;
   参数5 $zindex : z-index值;
   .className{ @include br(10,10,10,10); }
   或
   .className{ @include br(10,10,10,10,10); }  
```
z ( z-index层级 )<br>
```
例子 :
   .className{ @include z(10); }  
```
z1 ( z-index层级为10 )<br>
```
例子 :
   .className{ @include z1; }  
```
z2 ( z-index层级为20 )<br>
```
例子 :
   .className{ @include z2; }  
```
z3 ( z-index层级为30 )<br>
```
例子 :
   .className{ @include z3; }  
```
z4 ( z-index层级为40 )<br>
```
例子 :
   .className{ @include z4; }  
```
z5 ( z-index层级为50 )<br>
```
例子 :
   .className{ @include z5; }  
```
z6 ( z-index层级为60 )<br>
```
例子 :
   .className{ @include z6; }  
```
z-max ( z-index最高层级9999 )<br>
```
例子 :
   .className{ @include z-max; }  
```

### 字体的混合宏(_fonts.scss);

f ( 设置所有字体属性 )<br>
```
例子 :
  默认为 font 如果参数为一个数值则 设置 font-size;
  .className{ @include f(italic bold 12px/20px arial,sans-serif); }  
   或
  .className{ @include f(10); }  
```
fz ( 设置font-size )<br>
```
例子 :
  .className{ @include fz(10); }  
``` 
fa ( 设置font-family )<br>
```
例子 :
  默认参数为'Microsoft Yahei';
  .className{ @include fa(); }  
``` 
c ( 设置color )<br>
```
例子 :
  .className{ @include c(#fff); }  
``` 
fs ( 设置font-style )<br>
```
例子 :
  .className{ @include fs(bold); }  
```
fb ( 设置font-weight )<br>
```
例子 :
  .className{ @include fb(); }  
```
no-b ( 去掉font-weight )<br>
```
例子 :
  .className{ @include no-b; }  
```
ita ( 文字斜体 )<br>
```
例子 :
  .className{ @include ita; }  
```
no-fs ( 去掉文字风格 )<br>
```
例子 :
  .className{ @include no-fs; }  
```
lh ( 设置line-height )<br>
```
例子 :
  .className{ @include lh(10); }  
```

### border的混合宏(_border.scss);

bd ( 设置border )<br>
```
例子 :
   .className{ @include bd(1px solid #fff); }  
```
bdt ( 设置border-top )<br>
```
例子 :
   .className{ @include bdt(1px solid #fff); }  
```
bdr ( 设置border-right )<br>
```
例子 :
   .className{ @include bdr(1px solid #fff); }  
```
bdb ( 设置border-bottom )<br>
```
例子 :
   .className{ @include bdb(1px solid #fff); }  
```
bdl ( 设置border-left )<br>
```
例子 :
   .className{ @include bdl(1px solid #fff); }  
```
bdtb ( 设置border-top\border-bottom )<br>
```
例子 :
  第二参数不填 border-bottom == border-top 值一样
   .className{ @include bdtb(1px solid #fff); }
   或
   .className{ @include bdtb(1px solid #fff,1px solid #000); }  
```
bdrl ( 设置border-right\border-left )<br>
```
例子 :
  第二参数不填 border-left == border-right 值一样
   .className{ @include bdrl(1px solid #fff); }
   或
   .className{ @include bdrl(1px solid #fff,1px solid #000); }  
```
bdc ( 设置border-color )<br>
```
例子 :
   .className{ @include bdc(#000); }  
```
bdi ( 设置border-image )<br>
```
例子 :
   .className{ @include bdi(url(border.png) 30 30 round); }  
```
no-bd ( 取消边框 )<br>
```
例子 :
   .className{ @include no-bd; }  
```
no-bdt ( 取消上边框 )<br>
```
例子 :
   .className{ @include no-bdt; }  
``` 
no-bdr ( 取消右边框 )<br>
```
例子 :
   .className{ @include no-bdr; }  
``` 
no-bdb ( 取消下边框 )<br>
```
例子 :
   .className{ @include no-bdb; }  
``` 
no-bdl ( 取消左边框 )<br>
```
例子 :
   .className{ @include no-bdl; }  
``` 
no-bdtb ( 取消上边框&&下边框 )<br>
```
例子 :
   .className{ @include no-bdtb; }  
``` 
no-bdrl ( 取消右边框/左边框 )<br>
```
例子 :
   .className{ @include no-bdrl; }  
``` 
oln ( 设置outline )<br>
```
例子 :
   .className{ @include oln(#00FF00 dotted thick); }  
```
oln-c ( 设置outline-color )<br>
```
例子 :
   .className{ @include oln-c(#00FF00); }  
```
oln-r ( 设置outline-radius )<br>
```
例子 :
   .className{ @include oln-r(30); }  
```
oln-s ( 设置outline-style )<br>
```
例子 :
   .className{ @include oln-s(solid); }  
```
oln-w ( 设置outline-width )<br>
```
例子 :
   .className{ @include oln-w(30); }  
```
oln-o ( 设置outline-offset )<br>
```
例子 :
   .className{ @include oln-w(30); }  
```

### 打包默认(_resetpack.scss);

base ( 设置width/height/line-height )<br>
```
例子 :
  参数1 $content:number 设置 .content 的宽度;
  参数2 $unit:px 设置默认单位;
  参数3 $orange:#f60 设置默认橙色文字颜色、默认背景颜色;
  参数4 $yellow:$fff000 设置默认黄色文字颜色、默认背景颜色;
  参数5 $blue:#5fb3d2 设置默认蓝色文字颜色、默认背景颜色;
  参数6 $red:#ff546a 设置默认红色文字颜色、默认背景颜色;
  参数7 $gray:#ccc 设置默认灰色文字颜色、默认背景颜色;
  参数8 $disabled:#ccc 设置默认禁止颜色;
  参数9 $bor_color:#ccc 设置默认边框颜色;
  参数10 $format:- 设置默认连接-;
   @include base(1000);
```

### 清楚标签默认样式(_normalize.scss);

.className{ @include label; } 

### 混合缩写的混合宏(_group.scss);

whl ( 设置width/height/line-height )<br>
```
例子 :
   .className{ @include whl(10,10,10); }  
```
whfl ( 设置width/height/font-size/line-height )<br>
```
例子 :
   .className{ @include whfl(10,10,10,10); }  
```
whflc ( 设置width/height/font-size/line-height/color )<br>
```
例子 :
   .className{ @include whflc(10,10,10,10,#fff); }  
```
whflcb ( 设置width/height/font-size/line-height/color/font-weight )<br>
```
例子 :
   最后一个 font-weight 可不传参数默认 bold;
   .className{ @include whflcb(10,10,10,10,#fff); }  
```
hl ( 设置height/line-height )<br>
```
例子 :
   第二参数不传 line-height == height 
   .className{ @include hl(10); }
   或
   .className{ @include hl(10,10); }  
```
hflc ( 设置height/font-size/line-height/color )<br>
```
例子 :
   .className{ @include hflc(10,10,10,#fff); } 
```
wl ( 设置width/line-height )<br>
```
例子 :
   .className{ @include wl(10,10); } 
```
flh ( 设置font-szie/line-height )<br>
```
例子 :
   .className{ @include flh(10,10); } 
```
fc ( 设置font-size/color )<br>
```
例子 :
   .className{ @include flh(10,#fff); } 
```
flc ( 设置font-size/line-height/color )<br>
```
例子 :
   .className{ @include flc(10,10,#fff); } 
```
faflc ( 设置family/font-size/line-height/color = font )<br>
```
例子 :
   .className{ @include flc('宋体',10,10,#fff); } 
```

### 其他scss的混合宏(_other.scss);

vit ( vertical-align:top )<br>
```
例子 :
   .className{ @include vit; } 
```
vic ( vertical-align:middle )<br>
```
例子 :
   .className{ @include vic; } 
```
vib ( vertical-align:bottom )<br>
```
例子 :
   .className{ @include vib; } 
```
vertical-align ( 设置vertical-align )<br>
```
例子 :
   .className{ @include vertical-align(top); } 
```
over ( overflow:hidden; )<br>
```
例子 :
   .className{ @include over; } 
```
ofv ( overflow:visible !important; )<br>
```
例子 :
   .className{ @include ofv; } 
```
cur ( 鼠标手 )<br>
```
例子 :
   .className{ @include cur; } 
```
$support-for-iecur ( 鼠标默认 )<br>
```
例子 :
   .className{ @include def; } 
```
cursor ( 设置鼠标手 )<br>
```
例子 :
   .className{ @include cursor(pointer); } 
```
opa ( 设置opacity )<br>
```
例子 :
   参数1 number 0~1透明度;
   参数2 true(默认)/false 是否兼容ie,默认兼容ie;
   .className{ @include opa(0.8); }
   或
   .className{ @include opa(0.8,false); }
```
no-resize ( 禁止textarea拖动大小 )<br>
```
例子 :
   .className{ @include no-resize; } 
```

















### 完整例子展示:
```
@charset "UTF-8";
@import "./base_mixins/_base_mixins.scss";
$BG_ULR :"../i/";//路径;

/*
 * 谁看过弹层
 * Author tq
 * Date:20170616
 */

.seeMe-main{
    @include wh(820,482);
    @include bgc(#fff);
}
.seeMe-head{
    @include rel;
    @include h(52);
    @include flc(20,52,#fff);
    @include ti(30);
    @include bdb(1px solid #e9e9e9);
    @include bgi('#{$BG_ULR}new-head-bg.jpg');
}
.seeMe-close{
    @include abs((t:5,r:5,w:20,h:20));
    @include over;
    @include bgi('#{$BG_ULR}new-close.gif',$position:center center);
}

.seeMe-body{
    @include pad(19,0,0,29);
    @include h(410);
}

.seeMe-left{
    @include fl;
    @include w(311);
}

.seeMe-right{
    @include fl;
    @include w(450);
}
.seeMe-one{
    @include flc(18,30,#333);
    @include fb;
}
.seeMe-two{
    @include h(39);
    @include flc(16,32,#333)
}
.seeMe-three{
    @include f(0);
    @include mb(12);
}
.seeMe-four{
    @include flc(14,35,#666);
    .color_ff546a{
        @include fb;
    }
}

.seeMe-five{
    @include flc(16,35,#333);
    @include fb;
}
.seeMe-a{
    @include fc(14,#2c84dd);
    @include ml(25);
    @include no-b; 
    @include line-underline;
    &:hover{
        @include no-line;
    }
}

.seeMe-per{
    @include f(20);
    @include fb;
    @include vic;
    @include c(#ff546a);
}
%txt{
    @include inblock;
    @include wh(66,22);
    @include ti(11);
    @include flc(14,22,#666);
    @include mr(6);
    @include over;
}
.seeMe-shut{
    @extend %txt;
    @include bgi('#{$BG_ULR}new-shut-bg.jpg');
}
.seeMe-open{
    @extend %txt;
    @include c(#ff546a);
    @include bgi('#{$BG_ULR}new-open-bg.jpg');
}

.seeMe-2code{
    @include wh(346-156,208-20);
    @include pad(20,0,0,156);
    @include mt(6);
    @include ml(32);
    @include bgi('#{$BG_ULR}new-people.jpg');
}

.seeMe-2codeImg{
    @include wh(170);
}

.seeMe-picMain{
    @include pt(11);
    @include bgi('#{$BG_ULR}new-use-bg.jpg');
}

.seeMe-pics{
    @include rel;
    @include mar(0,0,0,11);
    @include wh(260);
    @include over;
}
.seeMe-ul{
    @include pad(36,0,0,0);
    li{
        @include fl;
        @include wh(62);
        @include mr(8);
        @include over;
        @include bd(1px solid #e6e6e6);
        @include cur;
    }
}

.seeMe-praise{
    @include abs((t:0,r:0,w:80,h:32,z:10));
    @include tac;
    @include bdrs(5);
    @include bgc(#ff5470);
    @include cur;
    .praise-txt{
        @include inblock;
        @include h(32);
        @include flc(18,32,#fff);
        @include pl(30);
        @include bgi('#{$BG_ULR}new-heart-ico.png',$position:0 center);
    }

}
.praise-like{
    .praise-txt{
        @include f(14);
    }
    .a{
        @include bgc(rgba(0,0,0,0.2));
    }
}
```
