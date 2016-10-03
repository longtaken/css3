# css3
css3动画

###transform(案例-transform.html)
Transform字面上就是变形。<br>
在CSS3中transform主要包括以下几种：<br>
旋转rotate、扭曲skew、缩放scale和移动translate以及矩阵变形matrix。<br>
语法：<br>
transform ： none | <transform-function> [ <transform-function> ]* <br>
transform: rotate | scale | skew | translate |matrix;<br>
####一、旋转rotate
rotate(<angle>) ：通过指定的角度参数对原元素指定一个2D rotation（2D 旋转），需先有transform-origin属性的定义。transform-origin定义的是旋转的基点，其中angle是指旋转角度，如果设置的值为正数表示顺时针旋转，如果设置的值为负数，则表示逆时针旋转。如：transform:rotate(30deg)<br>
###二、移动translate
移动translate我们分为三种情况：<br>
translate(x,y水平方向和垂直方向同时移动（也就是X轴和Y轴同时移动）;<br>
translateX(x)仅水平方向移动（X轴移动）;<br>
translateY(Y)仅垂直方向移动（Y轴移动）;<br>
1、translate(<translation-value>[, <translation-value>]) ：<br>
	如transform:translate(100px,20px)<br>
2、translateX(<translation-value>) ： <br>
	如：transform:translateX(100px)<br>
3、translateY(<translation-value>) ：<br>
	如：transform:translateY(20px):<br>
###三、缩放scale
缩放scale和移动translate是极其相似，缩放基数为1，如果其值大于1元素就放大，反之其值小于1，元素缩小。<br>
1、scale(<number>[, <number>])：如：transform:scale(2,1.5):<br>
2、scaleX(<number>) ： 如：transform:scaleX(2):<br>
3、scaleY(<number>) ： 如transform:scaleY(2):<br>
###四、扭曲skew
扭曲skew和translate、scale一样同样具有三种情况：
1、skew(<angle> [, <angle>]) 如：transform:skew(30deg,10deg):
2、skewX(<angle>) 如：transform:skewX(30deg)
3、skewY(<angle>) 如：transform:skewY（10deg）
###五、矩阵matrix
matrix(<number>, <number>, <number>, <number>, <number>, <number>) ： 以一个含六值的(a,b,c,d,e,f)变换矩阵的形式指定一个2D变换，相当于直接应用一个[a b c d e f]变换矩阵.如transform: matrix(1, 0, 0, 1, 30, 30)<br>
实际上transform: matrix(1, 0, 0, 1, 30, 30);就等同于transform: translate(30px, 30px)，上面的方法都是以matrix为基本实现的。
####改变元素基点transform-origin
主要作用在进行transform动作之前可以改变元素的基点位置，因为我们元素默认基点就是其中心位置，transform进行的rotate,translate,scale,skew,matrix等操作都是以元素自己中心位置进行变化的。需要在不同的位置对元素进行这些操作那么我们就可以使用transform-origin来对元素进行基点位置改变。<br>
transform-origin(X,Y):用来设置元素的运动的基点（参照点）。默认点是元素的中心点。其中X和Y的值可以是百分值,em,px，其中X也可以是字符参数值left,center,right；Y和X一样除了百分值外还可以设置字符值top,center,bottom，这个看上去有点像我们background-position设置一样；<br>

###transition(案例-transition.html)
transition主要包含四个属性值：<br>
执行变换的属性：transition-property,<br>
变换延续的时间：transition-duration,<br>
在延续时间段，变换的速率变化transition-timing-function,<br>
变换延迟时间transition-delay。<br>
####一、transition-property:
语法：transition-property ： none | all | [ <IDENT> ] [ ',' <IDENT> ]*<br>
transition-property是用来指定当元素其中一个属性改变时执行transition效果，其主要有以下几个值：none(没有属性改变)；all（所有属性改变）这个也是其默认值；indent（元素属性名）。
当其值为none时，transition马上停止执行<br>
当指定为all时，则元素产生任何属性值变化时都将执行transition效果<br>
ident是可以指定元素的某一个属性值<br>
####二、transition-duration:
语法：transition-duration ： <time> [, <time>]* 
transition-duration是用来指定元素 转换过程的持续时间，取值：<time>为数值，单位为s（秒）或者ms(毫秒),可以作用于所有元素，包括:before和:after伪元素。其默认值是0，也就是变换时是即时的。<br>
####三、transition-timing-function:
语法：transition-timing-function ： ease | linear | ease-in | ease-out | ease-in-out | cubic-bezier(<number>, <number>, <number>, <number>) [, ease | linear | ease-in | ease-out | ease-in-out | cubic-bezier(<number>, <number>, <number>, <number>)]* <br>
取值：
transition-timing-function的值允许你根据时间的推进去改变属性值的变换速率，transition-timing-function有6个可能值：<br>
1、ease：（逐渐变慢）默认值，ease函数等同于贝塞尔曲线(0.25, 0.1, 0.25, 1.0)<br>
2、linear：（匀速），linear 函数等同于贝塞尔曲线(0.0, 0.0, 1.0, 1.0).<br>
3、ease-in：(加速)，ease-in 函数等同于贝塞尔曲线(0.42, 0, 1.0, 1.0).<br>
4、ease-out：（减速），ease-out 函数等同于贝塞尔曲线(0, 0, 0.58, 1.0).<br>
5、ease-in-out：（加速然后减速），ease-in-out 函数等同于贝塞尔曲线(0.42, 0, 0.58, 1.0)<br>
6、cubic-bezier：（该值允许你去自定义一个时间曲线）， 特定的cubic-bezier曲线。 (x1, y1, x2, y2)四个值特定于曲线上点P1和点P2。所有值需在[0, 1]区域内，否则无效。<br>
####四、transition-delay:
语法：transition-delay ： <time> [, <time>]* 
transition-delay是用来指定一个动画开始执行的时间，也就是说当改变元素属性值后多长时间开始执行transition效果，其取值：<time>为数值，单位为s（秒）或者ms(毫秒)，其使用和transition-duration极其相似，也可以作用于所有元素，包括:before和:after伪元素。 默认大小是"0"，也就是变换立即执行，没有延迟。

###animation(案例-animation.html)







