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

body{font-size:12px;color:#333;font-family:'Microsoft Yahei','宋体','黑体',Arial, Helvetica, sans-serif;}
body,div,h1,h2,h3,h4,h5,h6,ul,ol,dl,dt,dd,table,td,p,input,button{margin:0px;padding:0px;}
h1,h2,h3,h4,h5,h6{font-size:100%;}
a{text-decoration:none;}
a:hover{text-decoration:underline;}
ul,ol{list-style-type:none;}
.fl{float:left;}
.fr{float:right;}
.cf:after{visibility:hidden;display:block;font-size:0;content:" ";clear:both;height:0;}
.cf{zoom:1;}
.hide{display:none;}
img{border:none;vertical-align:top;}
.f_12{font-size:12px;}
.f_14{font-size:14px;}
.f_16{font-size:16px;}
.f_18{font-size:18px;}
.f_20{font-size:20px;}
.f_22{font-size:22px;}
.f_YH{font-family:'microsoft yahei';}
.f_italic{font-style:italic;}
.color_000{color:#000;}
.color_333{color:#333;}
.color_666{color:#666;}
.color_999{color:#999;}
.color_4d97ef{color:#4d97ef;}
.color_2c81d6{color:#2c81d6;}
.color_e7417f{color:#e7417f;}
.color_ff546a{color:#ff546a;}
.txt_underline{text-decoration:underline;}
.mr_10{margin-right:10px;}

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