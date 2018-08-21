# base_mixins
[![](https://vsmarketplacebadge.apphb.com/version-short/uustoboy.base_mixins.svg?style=flat-square)]
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/uustoboy/base_mixins.svg?style=social&label=Star%20on%20Github)](https://github.com/uustoboy/base_mixins)
基于sass开发的简写、组合速写的混合宏<br>

### 全局设置参数:
$global-for-ie    : true(默认)/false;  ( 兼容老版ie ) <br>
$vendors          : webkit moz ms o;  ( 设置css3前缀 )<br>
$prefixWebkit     : true!default(默认)/false   ( 开启谷歌前缀:webkit前缀 )<br>
$prefixMozilla    : true !default(默认)/false; ( 开启火狐前缀:moz前缀 )<br>
$prefixMicrosoft  : true!default(默认)/false;  ( 开启IE前缀:ms前缀 )<br>
$prefixOpera      : true!default(默认)/false;  ( 开启opera前缀:o前缀 )<br>
$prefixNo         : true/false!default(默认); ( 默认前缀关闭 )<br>
$global-unit      : px;  ( 全局默认补全单位,如果设置默认单位为'rem'/'rpx'且不需要加'!important'可直接传值 全部值会自动转换)<br>
$designWidth      : 640; ( 移动转rem默认尺寸大小 ) <br>
$wxDesignWidth    : 750;    ( 微信小程序转rpx默认尺寸大小 ) <br>

### 动画的混合宏(_animation.scss):

keyframes ( 设置@keyframes 规则 )<br>
```
例子 :
   css3动画,只能写在调用页面,配合.css3( @style,@frames )使用
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
ani ( 设置animation )<br>
```
例子 :
   .className{ @include ani(keyframes 5s infinite); }
```
ani-name ( 设置animation-name )<br>
```
例子 :
   .className{ @include ani-name(keyframes-name); }
```
ani-dur ( 设置animation-duration )<br>
```
例子 :
   不传参数默认'0.2s';
   .className{ @include ani-dur(); }
   或
   .className{ @include ani-dur(0.5s); }
```
ani-time ( 设置animation-timing-function )<br>
```
例子 :
   不传参数默认'linear';
   .className{ @include ani-time(); }
   或
   .className{ @include ani-time(linear); }
```
ani-itc ( 设置animation-iteration-count )<br>
```
例子 :
   不传参数默认'1';
   .className{ @include ani-itc(); }
   或
   .className{ @include ani-itc(infinite); }
```
ani-dir ( 设置animation-direction )<br>
```
例子 :
   不传参数默认’alternate';
   .className{ @include ani-dir(); }
   或
   .className{ @include ani-dir(normal); }
```
ani-play ( 设置animation-play-state )<br>
```
例子 :
   不传参数默认'running';
   .className{ @include ani-play(); }
   或
   .className{ @include ani-play(paused); }
```
ani-del ( 设置animation-delay )<br>
```
例子 :
   不传参数默认'0.2s';
   .className{ @include ani-del(); }
   或
   .className{ @include ani-del(0.5s); }
```
ani-fill ( 设置animation-fill-mode )<br>
```
例子 :
   不传参数默认'forwards';
   .className{ @include ani-fill(); }
   或
   .className{ @include ani-fill(backwards); }
```

### 背景的混合宏(_background.scss):

bg ( 设置background )<br>
```
例子 :
   参数1 $color : 颜色值（没有默认颜色）;
   参数2 $img : 图片路径;
   参数3 $repeat : 'no-repeat'(默认) 设置background-repeat;
   参数4 $position : '0 0'(默认) 设置background-position;
   参数5 $ie6 : false(默认) 是否兼容png在ie6下添加gif;
   .className{ @include bg(#fff,'../i/a.jpg'); }
   或
   .className{ @include bg(#fff); }
```
no-bg ( 取消背景background:none )<br>
```
例子 :
    参数 $agr : true(默认) 是否添加!important
   .className{ @include no-bg; }
```
bgi ( 设置background-image )<br>
```
例子 :
  参数1 $img : 图片路径;
  参数2 $repeat : 'no-repeat'(默认) 设置background-repeat;
  参数3 $position : '0 0'(默认) 设置background-position;
  参数4 $ie6 : false(默认) 是否兼容png在ie6下添加gif;
  .className{ @include bgi('../i/new-close.gif',$position:center center); }
```
bgr ( 设置background-repeat )<br>
```
例子 :
  参数 $arg : no-repeat(默认) 图片平铺;
  .className{ @include bgr; }
```
bgz ( 设置background-size )<br/>
```
例子 :
   不传参数默认'cover';
   .className{ @include bgz(); }
   或
   .className{ @include bgz(contain); }
```
bgiz ( 设置background-image && background-size )<br>
```
例子 :
  参数1 $img : 图片路径;
  参数2 $repeat : 'no-repeat'(默认) 设置background-repeat;
  参数3 $position : '0 0'(默认) 设置background-position;
  参数4 $size : cover(默认) 设置background-size;
  .className{ @include bgiz('../i/new-close.gif',$position:center center); }
```
bg-clip ( 设置background-clip )<br>
```
例子 :
   不传参数默认'content-box';
   .className{ @include bg-clip(); }
   或
   .className{ @include bg-clip(padding-box); }
```
bgo ( 设置background-origin )<br>
```
例子 :
   不传参数默认'content-box';
   .className{ @include bgo(); }
   或
   .className{ @include bgo(border-box); }
```
bgp ( 设置background-position )<br>
```
例子 :
   不传参数默认'center cente';
   .className{ @include bgp(); }
   或
   .className{ @include bgp(center center); }
```
bgc  ( 设置背景颜色 )<br>
```
例子 :
   参数1 $color : 为颜色;
   参数2 $support-for-ie : true/false(默认为) 如果$global-for-ie:false 又想当前className的rgba兼容ie则传true;
   .className{ @include bgc(#fff); }
   或
   .className{ @include bgc(rgba(0,0,0,0.25)); }
   或
   $global-for-ie:false;
   .className{ @include bgc(rgba(0,0,0,0.25),true); }
```
max-img ( 用max-width来防止图片撑破容器 )<br>
```
例子 :
   .className{ @include max-img; }
```
bg-image ( 设置@2x/@3x 背景图片 )<br>
```
例子 :
    参数1 $url : 图片路径;
    参数2 $repeat : 'no-repeat' (默认) 设置background-repeat;
    参数3 $position : '0 0' (默认) 设置background-position;
   .className{ @include bg-image('../i/i/img.png'); }
```
fullscreen-bg ( 设置全屏大图背景 )<br>
```
例子 :
    参数1 $url : 图片路径;
    参数3 $position : '50% 50%'(默认) 设置background-position;
   .className{ @include fullscreen-bg('../i/i/img.png'); }
```
bg-sp ( css sprite:只能X轴、Y轴(默认Y轴) )<br>
```
例子 :
  参数1 $name : '.sprite-ico'(默认图标名) 设置class名;
  参数2 $number : 10 (默认值10) 循环图标个数;
  参数3 $mult : 2 (默认值2)  间隔距离;
  参数4 $startX : 0 (默认值0) x轴开始像素点;
  参数5 $startY : 0 (默认值0) y轴开始像素点;
  参数6 $dir : y (默认y轴) y 方向:X轴、Y轴、XY轴(x,y,xy);
  参数7 $bgz : false (默认false) 设置background-size;
  参数8 $url : false (默认false) 图片路径;
  参数9 $ie6 : false (默认false) 是否兼容png在ie6下添加gif;
  .sprite-ico{
     @include wh(163);
      @include bgi('../i/1.jpg');
  }
  @include bg-sp('.sprite-ico',5,163){ @include fl; };
  或者
  @include bg-sp('.sprite-ico',5,163,$dir:x);
```
bg-sp2 ( css sprite:矩阵图形(默认X轴开始) )<br>
```
例子 :
  参数1 $name : '.sprite-ico'(默认图标名) 设置class名;
  参数2 $y : 0 (默认值0) Y轴个数(行数);
  参数3 $x : 0 (默认值0) X轴个数(列数);
  参数4 $multY : 2 (默认值2) y轴间隔距离;
  参数5 $multX : 2 (默认值2) x轴间隔距离;
  参数6 $startX : 0(默认值0) x轴开始像素点;
  参数7 $startY : 0(默认值0) y轴开始像素点;
  参数8 $dir : y(默认y轴) y 方向:X轴、Y轴、XY轴(x,y,xy);
  参数9 $bgz : false(默认false) 设置background-size;
  参数10 $url : false(默认false) 图片路径;
  参数11 $ie6 : false(默认false) 是否兼容png在ie6下添加gif;
  .sprite-ico{
     @include wh(163);
      @include bgi('../i/1.jpg');
  }
  @include bg-sp('.sprite-ico',2,3,163){ @include fl; };
  或者
  @include bg-sp('.sprite-ico',2,3,163,$dir:x);
```
bgList-sp ( css sprite:只能X轴、Y轴(默认Y轴) )<br>
```
例子 :
  参数1 $list : () (默认空) 设置多个class名;
  参数2 $mult : 2 (默认值2)  间隔距离;
  参数3 $startX : 0 (默认值0) x轴开始像素点;
  参数4 $startY : 0 (默认值0) y轴开始像素点;
  参数5 $dir : y (默认y轴) y 方向:X轴、Y轴、XY轴(x,y,xy);
  参数6 $bgz : false (默认false) 设置background-size;
  参数7 $url : false (默认false) 图片路径;
  参数8 $ie6 : false (默认false) 是否兼容png在ie6下添加gif;
  .sprite-ico{
     @include wh(163);
      @include bgi('../i/1.jpg');
  }
  @include bgList-sp( ('.sprite-name',
                       '.sprite-sex',
                       '.sprite-age'),163){ @include fl; };
  或者
  @include bgList-sp( ('.sprite-name',
                       '.sprite-sex',
                       '.sprite-age'),163,$dir:x);
```
bgList-sp2 ( css sprite:矩阵图形(默认X轴开始) )<br>
```
例子 :
  参数1 $list : () (默认空) 设置多个class名;
  参数2 $y : 0 (默认值0) Y轴个数(行数);
  参数3 $x : 0 (默认值0) X轴个数(列数);
  参数4 $multY : 2 (默认值2) y轴间隔距离;
  参数5 $multX : 2 (默认值2) x轴间隔距离;
  参数6 $startX : 0(默认值0) x轴开始像素点;
  参数7 $startY : 0(默认值0) y轴开始像素点;
  参数8 $dir : y(默认y轴) y 方向:X轴、Y轴、XY轴(x,y,xy);
  参数9 $bgz : false(默认false) 设置background-size;
  参数10 $url : false(默认false) 图片路径;
  参数11 $ie6 : false(默认false) 是否兼容png在ie6下添加gif;
  .sprite-ico{
     @include wh(163);
      @include bgi('../i/1.jpg');
  }
    @include bgList-sp2( ('.sprite-name',
                          '.sprite-age',
                          '.sprite-sex',
                          '.sprite-native',
                          '.sprite-education',
                          '.sprite-married',),2,3,163){ @include fl; };
  或者
    @include bgList-sp2( ('.sprite-name',
                          '.sprite-age',
                          '.sprite-sex',
                          '.sprite-native',
                          '.sprite-education',
                          '.sprite-married',),2,3,163,$dir:y);
```

### 块的混合宏(_block.scss):

block ( 设置display:block )<br>
```
例子 :
   参数: $args:false(默认)/true 是否加!important;
   .className{ @include block; }
   或
   .className{ @include block(true); }
```
inline ( 设置display:inline )<br>
```
例子 :
   .className{ @include inline; }
```
inblock ( 设置inline-block )<br>
```
例子 :
   .className{ @include inblock; }
```
box ( 设置display:box )<br>
```
例子 :
   .className{ @include box; }
```
table ( 设置display:table )<br>
```
例子 :
   .className{ @include table; }
```
none ( 设置display:none )<br>
```
例子 :
   参数: $args:false(默认)/true 是否加!important;
   .className{ @include none; }
   或者
   .className{ @include none(true); }
```
show ( 设置display:block )<br>
```
例子 :
   .className{ @include show; }
```
hide ( 设置display:none )<br>
```
例子 :
   .className{ @include hide; }
```
box-sz ( 设置box-sizing )<br>
```
例子 :
   不传参数默认'border-box';
   .className{ @include box-sz(); }
   或
   .className{ @include box-sz(content-box); }
```
box-fx ( 设置box-flex:1 )<br>
```
例子 :
   不传参数默认'1';
   .className{ @include box-fx(1); }
   或
   .className{ @include box-fx(3); }
```
box-o ( 设置box-orient:block-axis )<br>
```
例子 :
   不传参数默认'horizontal';
   .className{ @include box-o(); }
   或
   .className{ @include box-o(block-axis); }
```
horizontal ( box-orient:horizontal )<br>
```
例子 :
   .className{ @include horizontal; }
```
vertical ( box-orient:vertical )<br>
```
例子 :
   .className{ @include vertical; }
```
reverse ( box-direction:reverse )<br>
```
例子 :
   .className{ @include reverse; }
```
box-dir ( 设置box-direction )<br>
```
例子 :
   不传参数默认'reverse';
   .className{ @include box-dir(); }
   或
   .className{ @include box-dir( inherit ); }
```
no-box-dir  ( 默认方向方向排列box-direction:normal )<br>
```
例子 :
   .className{ @include no-box-dir; }
```
box-a ( 设置box-align )<br>
```
例子 :
   不传参数默认'center';
   .className{ @include box-a(); }
   或
   .className{ @include box-a( baseline ); }
```
flex ( display:flex )<br>
```
例子 :
   .className{ @include flex; }
```
flexbox ( display:flexbox )<br>
```
例子 :
   .className{ @include flexbox; }
```
inflex ( display:inline-flex )<br>
```
例子 :
   .className{ @include inflex; }
```
fx ( 设置flex )<br>
```
例子 :
   不传参数默认'1';
   .className{ @include fx(); }
   或
   .className{ @include fx(2); }
```
fx-dir ( 设置flex-direction )<br>
```
例子 :
   不传参数默认'row';
   .className{ @include fx-dir(); }
   或
   .className{ @include fx-dir( column ); }
```
fx-row ( flex-direction:row )<br>
```
例子 :
   .className{ @include fx-row(); }
```
fx-w ( 设置flex-wrap )<br>
```
例子 :
   不传参数默认'wrap';
   .className{ @include fx-w(); }
   或
   .className{ @include fx-w( wrap-reverse ); }
```
fx-f ( 设置flex-flow )<br>
```
例子 :
   不传参数默认'row wrap';
   .className{ @include fx-f(); }
   或
   .className{ @include fx-f( row wrap-reverse ); }
```
jc ( 设置justify-content )<br>
```
例子 :
   不传参数默认'flex-start';
   .className{ @include jc(); }
   或
   .className{ @include jc( flex-end ); }
```
ai ( 设置align-items )<br>
```
例子 :
   不传参数默认'flex-start';
   .className{ @include ai(); }
   或
   .className{ @include ai( flex-end ); }
```
ac ( 设置align-content )<br>
```
例子 :
   不传参数默认'flex-start';
   .className{ @include ac(); }
   或
   .className{ @include ac( flex-end ); }
```
as ( 设置align-self )<br>
```
例子 :
   不传参数默认'1px';
   .className{ @include as(); }
   或
   .className{ @include as( 2 ); }
```
fx-start ( 设置flex-start )<br>
```
例子 :
   不传参数默认'jc';
   .className{ @include fx-start(); }
   或
   .className{ @include fx-start( ai ); }
   或
   .className{ @include fx-start( ac ); }
   或
   .className{ @include fx-start( as ); }
```
fx-end ( 设置flex-end )<br>
```
例子 :
   不传参数默认'jc';
   .className{ @include fx-end(); }
   或
   .className{ @include fx-end( ai ); }
   或
   .className{ @include fx-end( ac ); }
   或
   .className{ @include fx-end( as ); }
```
fx-center ( 设置flex-end )<br>
```
例子 :
   不传参数默认'jc';
   .className{ @include fx-center(); }
   或
   .className{ @include fx-center( ai ); }
   或
   .className{ @include fx-center( ac ); }
   或
   .className{ @include fx-center( as ); }
```
fx-between ( 设置space-between )<br>
```
例子 :
   不传参数默认'jc';
   .className{ @include fx-between(); }
   或
   .className{ @include fx-between( ai ); }
   或
   .className{ @include fx-between( ac ); }
   或
   .className{ @include fx-between( as ); }
```
fx-around ( 设置space-between )<br>
```
例子 :
   不传参数默认'jc';
   .className{ @include fx-around(); }
   或
   .className{ @include fx-around( ai ); }
   或
   .className{ @include fx-around( ac ); }
   或
   .className{ @include fx-around( as ); }
```
fx-baseline ( align-items:baseline )<br>
```
例子 :
   .className{ @include fx-baseline; }
```
fx-stretch ( 设置stretch )<br>
```
例子 :
   不传参数默认'ac';
   .className{ @include fx-stretch(); }
   或
   .className{ @include fx-stretch( ai ); }
```
odr ( 设置order )<br>
```
例子 :
   不传参数默认'1';
   .className{ @include odr(); }
   或
   .className{ @include odr( 2 ); }
```
fx-g ( 设置flex-grow )<br>
```
例子 :
   不传参数默认'1';
   .className{ @include fx-g(); }
   或
   .className{ @include fx-g( 2 ); }
```
fx-s ( 设置flex-shrink )<br>
```
例子 :
   不传参数默认'1';
   .className{ @include fx-s(); }
   或
   .className{ @include fx-s( 2 ); }
```
fx-b ( 设置flex-basis )<br>
```
例子 :
   不传参数默认'1';
   .className{ @include fx-b(); }
   或
   .className{ @include fx-b( 2 ); }
```
gd ( display:grid )<br>
```
例子 :
   .className{ @include gd; }
```
gd-t-cols ( 设置grid-template-columns )<br>
```
例子 :
   .className{ @include gd-t-cols( 150px 1fr ); }
```
gd-t-rows ( 设置grid-template-rows )<br>
```
例子 :
   .className{ @include gd-t-rows( 50px 1fr 30px ); }
```
gd-row-gap ( 设置grid-row-gap )<br>
```
例子 :
   .className{ @include gd-row-gap( 20px ); }
```
gd-column-gap ( 设置grid-column-gap )<br>
```
例子 :
   .className{ @include gd-column-gap( 20px ); }
```
gd-gap ( 设置grid-gap )<br>
```
例子 :
   .className{ @include gd-gap( 20px ); }
```
gd-col-start ( 设置grid-column-start )<br>
```
例子 :
   .className{ @include gd-col-start( 1 ); }
```
gd-col-end ( 设置grid-column-end )<br>
```
例子 :
   .className{ @include gd-col-end( auto ); }
```
gd-col ( 设置grid-column )<br>
```
例子 :
   .className{ @include gd-col( 50% 200px ); }
```
gd-row-start ( 设置grid-row-start )<br>
```
例子 :
   .className{ @include gd-row-start( 2 ); }
```
gd-row-end ( 设置grid-row-end )<br>
```
例子 :
   .className{ @include gd-row-end( 2 ); }
```
gd-row ( 设置grid-row )<br>
```
例子 :
   .className{ @include gd-row( 100px (30px 60px) ); }
```
gd-auto-rows ( 设置grid-auto-rows )<br>
```
例子 :
   .className{ @include gd-auto-rows( 1fr ); }
```
gd-t-areas ( 设置grid-template-areas )<br>
```
例子 :
   .className{ @include gd-t-areas( none ); }
```
ji ( 设置justify-items )<br>
```
例子 :
   .className{ @include ji( center ); }
```
js ( 设置justify-self )<br>
```
例子 :
   .className{ @include js( flex-start ); }
```

### 浮动混合宏(_clear.scss):

fl ( float:left )<br>
```
例子 :
   .className{ @include fl; }
```
fr ( float:left )<br>
```
例子 :
   .className{ @include fr; }
```
clear ( 清浮动clear )<br>
```
例子 :
   .className{ @include clear; }
```

### css3的混合宏(_css3.scss):

css3  ( css3前缀 )<br>
```
例子 :
   css3前缀:
    $style     :  css属性;
    $frames    :  css属性内容;
    $prefix    :  true(默认)/false 是否添加样式前缀,默认开启;
    $suffix    :  true/false(默认) 是否添加样式后缀,默认关闭;
  .className{ @include css3(display,box); }
   或
  .className{ @include css3(display,box,false,true); }
```
cnt ( 设置content )<br>
```
例子 :
   不传参数默认'';
   .className{ @include cnt(); }
   或
   .className{ @include cnt('123'); }
```
trs ( 设置transition )<br>
```
例子 :
   可不传参数默认‘all 0.3s ease’;
   .className{ @include trs(); }
   或
   .className{ @include trs(all 0.7s ease); }
```
trs-p ( 设置transition-property )<br>
```
例子 :
   .className{ @include trs-p(width); }
```
trs-dur ( 设置transition-property )<br>
```
例子 :
   .className{ @include trs-dur(0.2s); }
```
trs-tf ( 设置transition-timing-function )<br>
```
例子 :
   .className{ @include trs-tf(linear); }
```
trs-del ( 设置transition-delay )<br>
```
例子 :
   .className{ @include trs-del(0.2s); }
```
bdrs ( 设置border-radius )<br>
```
例子 :
   不传参数默认5px;
   .className{ @include bdrs(); }
   或
   .className{ @include bdrs(50); }
```
box-s ( 设置box-shadow )<br>
```
例子 :
   不传参数默认'0 0 4px rgba(0,0,0,.3)';
   .className{ @include box-s(); }
   或
   .className{ @include box-s(10px 10px 4px rgba(0,0,0,.3)); }
```
设置text-s ( 设置text-shadow )<br>
```
例子 :
   不传参数默认'0 0 4px rgba(0,0,0,.3)';
   .className{ @include text-s(); }
   或
   .className{ @include t-sh(10px 10px 4px rgba(0,0,0,.3)); }
```
no-box-s ( 设置box-shadow:none )<br>
```
例子 :
   .className{ @include no-box-s; }
```
no-text-s ( 设置text-shadow:none )<br>
```
例子 :
   .className{ @include no-text-s; }
```
usr-s ( 设置user-select )<br>
```
例子 :
   不传参数默认'text';
   .className{ @include usr-s(); }
   或
   .className{ @include usr-s(); }
```
user-s-ban ( 设置禁止文本被选择 )<br>
```
例子 :
   不传参数默认'text';
   .className{ @include user-s-ban(); }
```
trf ( 设置transform )<br>
```
例子 :
   .className{ @include trf(rotate(7deg)); }
```
trf-o ( 设置transform-origin )<br>
```
例子 :
   .className{ @include trf-o(20% 40%); }
```
trf-s ( 设置transform-style; )<br>
```
例子 :
   不传参数默认'preserve-3d';
   .className{ @include trf-s(); }
   或
   .className{ @include trf-s(flat); }
```
bv ( 设置backface-visibility )<br>
```
例子 :
   不传参数默认'hidden';
   .className{ @include bv(); }
   或
   .className{ @include bv(visible); }
```
pec ( 设置perspective )<br>
```
例子 :
   不传参数默认'none';
   .className{ @include pec(); }
   或
   .className{ @include pec(500); }
```
pec-o ( 设置perspective-origin )<br>
```
例子 :
   不传参数默认'50% 50%';
   .className{ @include pec-o(); }
   或
   .className{ @include pec-o(30% 60%); }
```
pec-ox ( 设置perspective-origin-x )<br>
```
例子 :
   不传参数默认'50%';
   .className{ @include pec-ox(); }
   或
   .className{ @include pec-ox(30%); }
```
pec-oy ( 设置perspective-origin-y )<br>
```
例子 :
   不传参数默认'50%';
   .className{ @include pec-oy(); }
   或
   .className{ @include pec-oy(30%); }
```
rotate ( 设置transform:rotate )<br>
```
例子 :
   .className{ @include rotate(50deg); }
```
pe ( 设置pointer-events )<br>
```
例子 :
    参数 $arg : none (默认none) 设置pointer-events;
   .className{ @include pe; }
```
filter ( 设置filter )<br>
```
例子 :
   .className{ @include filter( grayscale(100%) ); }
```
blur ( 设置模糊 )<br>
```
例子 :
    参数 $blur : 10px (默认10px) 设置模糊像素;
   .className{ @include blur(); }
```
grayscale ( 设置图片灰色 )<br>
```
例子 :
    参数 $args : 100% (默认100%) 设置grayscale;
   .className{ @include grayscale(); }
```
beauty-placeholder ( 设置placeholder )<br>
```
例子 :
    参数1 $fz : 12 (默认12px) 设置font-size;
    参数2 $color : #999 (默认#999) 设置color;
    参数3 $align : left (默认left) 设置text-align;
   .className{ @include beauty-placeholder(12,red,left); }
```
beauty-placeholder2 ( 自定义placeholder )<br>
```
例子 :
   @include beauty-placeholder2{
       color:red;
       font-size:12px;
   }
```
beauty-select ( 设置选中文本 )<br>
```
例子 :
    参数1 $fz : 12 (默认12px) 设置font-size;
    参数2 $color : #999 (默认#999) 设置color;
    参数3 $align : left (默认left) 设置text-align;
   @include beauty-placeholder2{
       color:red;
       font-size:12px;
   }
```
scrollbar ( 设置css3滚动条 )<br>
```
例子 :
   例子 :
    @include scrollbar(scrollbar-track){
       #{$browser}box-shadow: inset 0 0 6px rgba(0,0,0,0.3);
       background-color: #F5F5F5;
    };
    @include scrollbar(scrollbar){
       width: 12px;
    };
    @include scrollbar(scrollbar-thumb){
       #{$browser}border-radius: 10px;
       #{$browser}box-shadow: inset 0 0 6px rgba(0,0,0,.3);
       background-color: #fbd0c9;
    };
```

### 文本的混合宏(_text.scss):

tofl ( 超出一行.... )<br>
```
例子 :
   .className{ @include tofl; }
```
erow ( 多行显示... )<br>
```
例子 :
   不传参数默认2行;
   .className{ @include erow(); }
   或
   .className{ @include erow(3); }
```
ws ( 强制一行 )<br>
```
例子 :
   参数 $arg : nowrap (默认) 设置white-space;
   .className{ @include ws(); }
```
wm ( 文字排列方式 )<br>
```
例子 :
   参数 $arg : normal (默认) 设置writing-mode;
   .className{ @include ws(); }
```
bword ( 强制折行 )<br>
```
例子 :
   .className{ @include bword; }
```
wdw ( 断行 )<br>
```
例子 :
   .className{ @include wdw; }
```
hide-text ( 隐藏文字 )<br>
```
例子 :
   .className{ @include hide-text(); }
```
ti ( 设置text-indent )<br>
```
例子 :
   不传参数默认'2em';
   .className{ @include ti(); }
   或
   .className{ @include ti(4px); }
```
replace-text ( 设置text-indent  )<br>
```
例子 :
   参数1 $image: 图片路径;
   参数2 $x: 50%(默认) 图片x轴;
   参数3 $y: 50%(默认) 图片y轴;
   .className{ @include replace-text('../i/a.jpg',10px,220px); }
```
tal ( text-align:left )<br>
```
例子 :
   .className{ @include tal; }
```
tar ( text-align:right )<br>
```
例子 :
   .className{ @include tar; }
```
tac ( text-align:center )<br>
```
例子 :
   .className{ @include tac; }
```
ta ( 设置text-align )<br>
```
例子 :
   不传参数默认'left';
   .className{ @include ta()};
   或
   .className{ @include ta(right); }
```
tj ( 设置text-justify  )<br>
```
例子 :
   参数 $arg : auto(默认) 设置text-justify;
   .className{ @include tj(); }
```
td ( 设置text-decoration )<br>
```
例子 :
   不传参数默认'line-through';
   .className{ @include td()};
   或
   .className{ @include td(overline); }
```
line-over ( text-decoration:overline )<br>
```
例子 :
   .className{ @include line-over; }
```
line-del ( text-decoration:line-through )<br>
```
例子 :
   .className{ @include line-del; }
```
line-underline ( text-decoration:underline )<br>
```
例子 :
   .className{ @include line-underline; }
```
line-blink ( text-decoration:blink )<br>
```
例子 :
   .className{ @include line-blink; }
```
no-line ( text-decoration:none !important )<br>
```
例子 :
   .className{ @include no-line; }
```

### 宽高的混合宏(_size.scss):

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
mah ( 设置max-height )<br>
```
例子 :
   .className{ @include mah(12); }
```
maw ( 设置max-width )<br>
```
例子 :
   .className{ @include maw(12); }
```
mih ( 设置min-height )<br>
```
例子 :
   .className{ @include mih(12); }
```
miw ( 设置min-width )<br>
```
例子 :
   .className{ @include miw(12); }
```
size ( 设置width/height )<br>
```
例子 :
    参数1 $width
    参数2 $height (可不写,width等于height值)
   .className{ @include wh(12,30); }
   或者
   .className{ @include wh(12); }
```

### px转rem的混合宏(_rem.scss);
px2rem ( px转rem )<br>
```
例子 :
    需要页面引入'hotcss.js';
    参数1 $px : 转换数字,px单位可不写
    参数2 $important : true/false(默认) 是否加!important
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
   参数1 $px : 转换数字,px单位可不写
   参数2 $important : true/false(默认) 是否加!important
   $designWidth : 640;
   .className{ width : px2rem(100); }
   或
   .className{ @include w(px2rpx(100,true)); }
```
gpx2rpx ( 简单rpx多值转行 )<br>
```
例子 :
   .className{ @include pal(gpx2rpx(10,10,10,10)); }
   或
   .className{ @include margin:gpx2rpx(10,10,10,10); }
```

### 定位的混合宏(_position.scss);

position ( 设置position )<br>
```
例子 :
   参数1 $position : position的属性;
   参数2 $args :  json 可传(t:0,l:0,b:0,r:0,w:10,h:10,z:10)7个值
   .className{ @include position(absolute,(t:10px,l:0px,z:5)); }
```
abs ( position: absolute )<br>
```
例子 :
   参数 $args :  json 可传(t:0,l:0,b:0,r:0,w:10,h:10,z:10)几个值
   .className{ @include position(absolute,(t:10px,l:0px,z:5)); }
```
rel ( position: relative )<br>
```
例子 :
   参数 $args :  json 可传(t:0,l:0,b:0,r:0,w:10,h:10,z:10)几个值
   .className{ @include position(absolute,(t:10px,l:0px,z:5)); }
```
fixed ( position: fixed )<br>
```
例子 :
   参数 $args :  json 可传(t:0,l:0,b:0,r:0,w:10,h:10,z:10)几个值
   .className{ @include position(absolute,(t:10px,l:0px,z:5)); }
```
t ( 设置top值 )<br>
```
例子 :
   .className{ @include t(10); }
```
l ( 设置left值 )<br>
```
例子 :
   .className{ @include l(10); }
```
b ( 设置bottom值 )<br>
```
例子 :
   .className{ @include b(10); }
```
r ( 设置right值 )<br>
```
例子 :
   .className{ @include r(10); }
```
tl ( 设置top & left值 )<br>
```
例子 :
   参数1 $top : top值;
   参数2 $left : left值;
   参数3 $zindex : z-index值;
   .className{ @include tl(10,10); }
   或
   .className{ @include tl(10,10,10); }
```
rl ( 设置right & left值 )<br>
```
例子 :
   参数1 $right : right值;
   参数2 $left : left值;
   参数3 $zindex : z-index值;
   .className{ @include rl(10,10); }
   或
   .className{ @include rl(10,10,10); }
```
bl ( 设置bottom & left值 )<br>
```
例子 :
   参数1 $bottom : bottom值;
   参数2 $left : left值;
   参数3 $zindex : z-index值;
   .className{ @include bl(10,10); }
   或
   .className{ @include bl(10,10,10); }
```
br ( 设置bottom & right值 )<br>
```
例子 :
   参数1 $bottom : bottom值;
   参数2 $right : left值;
   参数3 $zindex : z-index值;
   .className{ @include br(10,10,10); }
   或
   .className{ @include br(10,10,10); }
```
trbl ( 设置top & left & bottom & right值 )<br>
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
z ( 设置z-index )<br>
```
例子 :
   .className{ @include z(10); }
```
z1 ( z-index:10 )<br>
```
例子 :
   .className{ @include z1; }
```
z2 ( z-index:20 )<br>
```
例子 :
   .className{ @include z2; }
```
z3 ( z-index:30 )<br>
```
例子 :
   .className{ @include z3; }
```
z4 ( z-index:40 )<br>
```
例子 :
   .className{ @include z4; }
```
z5 ( z-index:50 )<br>
```
例子 :
   .className{ @include z5; }
```
z6 ( z-index:60 )<br>
```
例子 :
   .className{ @include z6; }
```
z-max ( z-index:9999 )<br>
```
例子 :
   .className{ @include z-max; }
```

### 字体的混合宏(_fonts.scss);

f ( 设置font || font-size )<br>
```
例子 :
  默认为 font 如果参数为一个数值则设置 font-size;
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
  参数1 $color : #000 (默认#000) 设置color;
  参数2 $hovercolor : false (默认false) 是否设置hover颜色;
  .className{ @include c(#fff); }
  或
  .className{ @include c(#fff,#999); }
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
no-b ( font-weight: normal )<br>
```
例子 :
  .className{ @include no-b; }
```
ita ( font-style:italic )<br>
```
例子 :
  .className{ @include ita; }
```
no-fs ( font-style:normal )<br>
```
例子 :
  .className{ @include no-fs; }
```
lh ( 设置line-height )<br>
```
例子 :
  .className{ @include lh(10); }
```
normal-font ( 设置正常字体样式 )<br>
```
例子 :
  .className{ @include normal-font; }
```
assist-font ( 设置辅助性文字(灰色) )<br>
```
例子 :
  参数1 $color : #b0b0b0 (默认) 设置color;
  参数2 $$fz : 14(默认14px) 设置font-size;
  .className{ @include assist-font(#ccc,14); }
```
transparent-text ( 设置文字透明 )<br>
```
例子 :
  .className{ @include transparent-text; }
```
ls ( 设置letter-spacing )<br>
```
例子 :
  .className{ @include ls(10); }
```

### 边框的混合宏(_border.scss);

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
bdtb ( 设置border-top & border-bottom )<br>
```
例子 :
   参数1 $args1 : 设置border-top;
   参数2 $args2 : 设置border-bottom(可不写,border-bottom == border-top);
   .className{ @include bdtb(1px solid #fff); }
   或
   .className{ @include bdtb(1px solid #fff,1px solid #000); }
```
bdrl ( 设置border-right & border-left )<br>
```
例子 :
   参数1 $args1 : 设置border-right;
   参数2 $args2 : 设置border-left(可不写,border-left == border-right);
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
no-bd ( 取消边框border:none )<br>
```
例子 :
   .className{ @include no-bd; }
```
no-bdt ( 取消上边框border-top:none )<br>
```
例子 :
   .className{ @include no-bdt; }
```
no-bdr ( 取消右边框border-right:none )<br>
```
例子 :
   .className{ @include no-bdr; }
```
no-bdb ( 取消下边框border-bottom:none )<br>
```
例子 :
   .className{ @include no-bdb; }
```
no-bdl ( 取消左边框border-left:none )<br>
```
例子 :
   .className{ @include no-bdl; }
```
no-bdtb ( 取消上边框 & 下边框 border-top:none & border-bottom:none  )<br>
```
例子 :
   .className{ @include no-bdtb; }
```
no-bdrl ( 取消右边框 & 左边框 border-right:none & border-left:none )<br>
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
cut-line ( 分割线 | )<br>
```
例子 :
    参数1 $mar : 0 10px (默认) 设置margin;
    参数2 $color : #999 (默认#999) 设置color;
    参数3 $fz : 14 (默认14px) 设置font-size;
   .className{ @include cut-line(0 10,#999,14); }
```
cut-line2 ( 分割线 / (面包屑导航) )<br>
```
例子 :
    参数1 $pad : 0 10px (默认) 设置;
    参数2 $color : #ccc (默认#ccc) 设置color;
    参数3 $fz : 14 (默认14px) 设置font-size;
   .className{ @include cut-line2(0 10,#999,14); }
```

### 边距的混合宏(_box.scss);
mar ( 设置margin )<br>
```
例子 :
   .className{ @include mar(30); }
   或
   多值情况:
   .className{ @include mar(30 10 50 30); }
```
pad ( 设置padding )<br>
```
例子 :
   .className{ @include pad(30); }
   或
   多值情况:
   .className{ @include pad(30 10 5030); }
```
mt ( 设置margin-top )<br>
```
例子 :
   .className{ @include mt(30); }
```
mr ( 设置margin-right )<br>
```
例子 :
   .className{ @include mr(30); }
```
mb ( 设置margin-bottom )<br>
```
例子 :
   .className{ @include mb(30); }
```
ml ( 设置margin-left )<br>
```
例子 :
   .className{ @include ml(30); }
```
pt ( 设置padding-top )<br>
```
例子 :
   .className{ @include pt(30); }
```
pr ( 设置padding-right )<br>
```
例子 :
   .className{ @include pr(30); }
```
pb ( 设置padding-bottom )<br>
```
例子 :
   .className{ @include pb(30); }
```
pl ( 设置padding-left )<br>
```
例子 :
   .className{ @include pl(30); }
```
mtb ( 设置margin-top && margin-bottom )<br>
```
例子 :
   参数1 $size1 : number 设置margin-top;
   参数2 $size2 : number(默认margin-bottom = margin-top) 设置margin-bottom;
   .className{ @include mtb(30); }
   或
   .className{ @include mtb(30 10); }
```
mlr ( 设置margin-left && margin-right )<br>
```
例子 :
   参数1 $size1 : number 设置margin-left;
   参数2 $size2 : number(默认margin-right = margin-left) 设置margin-right;
   .className{ @include mlr(30); }
   或
   .className{ @include mlr(30 10); }
```
ptb ( 设置padding-top && padding-bottom )<br>
```
例子 :
   参数1 $size1 : number 设置padding-top;
   参数2 $size2 : number(默认padding-bottom = padding-top) 设置padding-bottom;
   .className{ @include ptb(30); }
   或
   .className{ @include ptb(30,10); }
```
plr ( 设置padding-left && padding-right )<br>
```
例子 :
   参数1 $size1 : number 设置padding-left;
   参数2 $size2 : number(默认padding-right = padding-left) 设置padding-right;
   .className{ @include plr(30); }
   或
   .className{ @include plr(30 10); }
```

### reset打包的混合宏(_resetpack.scss);

base ( 设置项目初始化 )<br>
```
例子 :
  参数1 $content:number 设置 .content 的宽度;
  参数2 $unit : px 设置默认单位;
  参数3 $orange : #f60 设置默认橙色文字颜色、默认背景颜色;
  参数4 $yellow : $fff000 设置默认黄色文字颜色、默认背景颜色;
  参数5 $blue : #5fb3d2 设置默认蓝色文字颜色、默认背景颜色;
  参数6 $red : #ff546a 设置默认红色文字颜色、默认背景颜色;
  参数7 $gray : #ccc 设置默认灰色文字颜色、默认背景颜色;
  参数8 $disabled : #ccc 设置默认禁止颜色;
  参数9 $bor_color : #ccc 设置默认边框颜色;
  参数10 $format : - 设置默认连接-;
  @include base(1000);
```

### 清除标签的混合宏(_normalize.scss);
label ( 清除标签默认属性 )<br>
```
例子 :
   @include label;
```
pc-label ( 清除pc标签默认属性 )<br>
```
例子 :
   @include pc-label;
```
mobile-label ( 清除mobile标签默认属性 )<br>
```
例子 :
   @include mobile-label;
```

### 混合缩写的混合宏(_group.scss);
whl ( 设置width & height & line-height )<br>
```
例子 :
   .className{ @include whl(10,10,10); }
```
whfl ( 设置width & height & font-size & line-height )<br>
```
例子 :
   .className{ @include whfl(10,10,10,10); }
```
whflc ( 设置width & height & font-size & line-height & color )<br>
```
例子 :
   .className{ @include whflc(10,10,10,10,#fff); }
```
whflcb ( 设置width & height & font-size & line-height & color & font-weight )<br>
```
例子 :
   最后一个 font-weight 可不传参数默认'bold';
   .className{ @include whflcb(10,10,10,10,#fff); }
```
hl ( 设置height & line-height )<br>
```
例子 :
   参数1 $height : 设置height
   参数2 $line-height 设置line-height(可不写,line-height == height)
   .className{ @include hl(10); }
   或
   .className{ @include hl(10,10); }
```
hflc ( 设置height & font-size & line-height & color )<br>
```
例子 :
   .className{ @include hflc(10,10,10,#fff); }
```
hflcb ( 设置height & font-size & line-height & color && font-weight )<br>
```
例子 :
   .className{ @include hflc(10,10,10,#fff); }
```
wl ( 设置width & line-height )<br>
```
例子 :
   .className{ @include wl(10,10); }
```
flh ( 设置font-szie & line-height )<br>
```
例子 :
   .className{ @include flh(10,10); }
```
fc ( 设置font-size & color )<br>
```
例子 :
   .className{ @include flh(10,#fff); }
```
flc ( 设置font-size & line-height & color )<br>
```
例子 :
   .className{ @include flc(10,10,#fff); }
```
fcb ( 设置font-size & color & font-weight )<br>
```
例子 :
   .className{ @include fcb(10,#fff); }
```
flcb ( 设置font-size & line-height & color & font-weight )<br>
```
例子 :
   .className{ @include flcb(10,10,#fff); }
```
faflc ( 设置family & font-size & line-height & color & font )<br>
```
例子 :
   .className{ @include flc('宋体',10,10,#fff); }
```
mawh ( 设置max-width & max-height )<br>
```
例子 :
   .className{ @include mawh(100%,100%); }
```
miwh ( 设置min-width & min-height )<br>
```
例子 :
   .className{ @include miwh(100%,100%); }
```
mmw ( 设置min-width & max-width)<br>
```
例子 :
   .className{ @include mmw(100%,100%); }
```

### 其他的混合宏(_other.scss);
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
over-x ( x轴截断 )<br>
```
例子 :
   .className{ @include over-x; }
```
over-y ( y轴截断 )<br>
```
例子 :
   .className{ @include over-y; }
```
cur ( 鼠标手 )<br>
```
例子 :
   .className{ @include cur; }
```
$def ( 鼠标默认 )<br>
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
   参数1 $opacity : 0.8(默认值) 0~1透明度;
   参数2 $support-for-ie : true/false(默认)  如果$global-for-ie:false 又想当前className的opacity兼容ie则传true;
   .className{ @include opa(0.8); }
   或
   $global-for-ie:false;
   .className{ @include opa(0.8,true); }
```
no-resize ( 禁止textarea拖动大小resize: none )<br>
```
例子 :
   .className{ @include no-resize; }
```
first-letter ( 首字下沉 )<br>
```
例子 :
    参数 $fz : 6em (默认6em) 设置font-szie;
   .className{ @include first-letter(2em); }
```
first-line ( 特殊标记段落第一行 )<br>
```
例子 :
    参数 $color : red (默认红色) 设置color;
   .className{ @include first-line(#333); }
```

### 圆形的混合宏(_round.scss);
round ( 设置圆形 )<br>
```
例子 :
   .className{ @include round(30); }
```
roundc ( 设置圆形 & 背景色 )<br>
```
例子 :
   .className{ @include roundc(30,#000); }
```

### 三角形的混合宏(_triangle.scss);
triangle-up ( 上三角圆形 )<br>
```
例子 :
  参数1 $w : 宽度;
  参数2 $h : 高度;
  参数3 $color : 颜色;
  .className{ @include triangle-up( 10,10,#000 ); }
```
triangle-right ( 右三角圆形 )<br>
```
例子 :
  参数1 $w : 宽度;
  参数2 $h : 高度;
  参数3 $color : 颜色;
  .className{ @include triangle-right( 10,10,#000 ); }
```
triangle-bottom ( 下三角圆形 )<br>
```
例子 :
  参数1 $w : 宽度;
  参数2 $h : 高度;
  参数3 $color : 颜色;
  .className{ @include triangle-bottom( 10,10,#000 ); }
```
triangle-left ( 左三角圆形 )<br>
```
例子 :
  参数1 $w : 宽度;
  参数2 $h : 高度;
  参数3 $color : 颜色;
  .className{ @include triangle-left( 10,10,#000 ); }
```
triangle-topleft ( 左上三角圆形 )<br>
```
例子 :
  参数1 $size : 边框线;
  参数2 $color : 颜色;
  .className{ @include triangle-topleft( 10,#000 ); }
```
triangle-topright ( 右上三角圆形 )<br>
```
例子 :
  参数1 $size : 边框线;
  参数2 $color : 颜色;
  .className{ @include triangle-topright( 10,#000 ); }
```
triangle-bottomleft ( 左下三角圆形 )<br>
```
例子 :
  参数1 $size : 边框线;
  参数2 $color : 颜色;
  .className{ @include triangle-bottomleft( 10,#000 ); }
```
triangle-bottomright ( 右下三角圆形 )<br>
```
例子 :
  参数1 $size : 边框线;
  参数2 $color : 颜色;
  .className{ @include triangle-bottomright( 10,#000 ); }
```
---

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

@include base();

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
### 感谢
- [SassMagic](https://github.com/W3cplus/SassMagic) -- 感谢 [W3cplus](https://github.com/W3cplus)
- [mylus](https://github.com/linx4200/mylus) -- 感谢 [liuxinran](https://github.com/linx4200)
- [postcss-crip](https://github.com/johnie/postcss-crip) -- 感谢 [Johnie Hjelm](https://github.com/johnie)
- [hotcss](https://github.com/imochen/hotcss) -- 感谢 [墨尘](https://github.com/imochen)
- [CSS常用Mixin封装](https://juejin.im/post/5a31f53f51882555cc41deda?utm_source=gold_browser_extension) -- 感谢 [白小明](https://juejin.im/user/593399e7a0bb9f0058d57801)
