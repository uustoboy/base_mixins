更新记录
=======
## 1.0.4 (2018-12-18)

添加基础变量:
* `$c-link`    : <font color=#72ACE3>#72ACE3</font>;<br/>
* `$c-white`   : #fff;<br/>
* `$c-black`   : <font color=#000>#000</font>;<br/>
* `$c-gray`    : <font color=#999>#999</font>;<br/>
* `$c-dark`    : <font color=#333>#333</font>;<br/>
* `$c-disabled`: <font color=#666>#666</font>;<br/>
* `$c-blue`    : <font color=#3B91FF>#3B91FF</font>;<br/>
* `$c-green`   : <font color=#13CE66>#13CE66</font>;<br/>
* `$c-yellow`  : <font color=#FFAE00>#FFAE00</font>;<br/>
* `$c-orange`  : <font color=#e8590c>#e8590c</font>;<br/>
* `$c-red`     : <font color=#E11617>#E11617</font>;<br/>
* `$c-pink`    : <font color=#c2255c>#c2255c</font>;<br/>
* `$c-grape`   : <font color=#9c36b5>#9c36b5</font>;<br/>
* `$c-violet`  : <font color=#6741d9>#6741d9</font>;<br/>
* `$c-indigo`  : <font color=#3b5bdb>#3b5bdb</font>;<br/>
* `$c-cyan`    : <font color=#0c8599>#0c8599</font>;<br/>
* `$c-teal`    : <font color=#099268>#099268</font>;<br/>
* `$c-lime`    : <font color=#66a80f>#66a80f</font>;<br/>
* `$f-value`   : 14;<br/>
* `$lh-value`  : 18;<br/>
* `$bdrs-value`: 5;<br/>

## 1.0.5 (2019-01-08)

修改@include base(<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$red : $c-red,<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$blue : $c-blue,<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$yellow : $c-yellow,<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$orange : $c-orange,<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$gray : $c-gray, <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$disabled : $c-dark,<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$bor_color : $c-dark<br/>
); 颜色值与_var.scss 颜色变量值同步;

## 1.0.6 (2019-02-01)

修改小程序rpx转值;