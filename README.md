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

### 动画:
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
    例子 :
   .className{ @include ani-dur(0.2s); }  
```
ani-time ( animation动画速度形式 )<br>
```
    例子 :
   .className{ @include ani-time(linear); }  
```
ani-itc ( animation动画播放次数 )<br>
```
    例子 :
   .className{ @include ani-itc(1); }  
```
ani-dir ( animation动画轮流反向播放动画 )<br>
```
    例子 :
   .className{ @include ani-dir(alternate); }  
```
ani-play ( animation动画"播放"或"暂停" )<br>
```
    例子 :
   .className{ @include ani-play(running); }  
```
ani-del ( animation动画延迟时间设置 )<br>
```
    例子 :
   .className{ @include ani-del(0.2s); }  
```
ani-fill ( animation动画运动完成后的状态设置 )<br>
```
    例子 :
   .className{ @include ani-fill(forwards); }  
```