### JS异步加载的三种方法
+ 　默认正常模式下下，JS是同步加载的，即优先加载JS，只有当JS文件下载完，dom和css才开始加载，当某些时候我们需要JS异步加载,我们可以通过以下方式来设置异步加载,不同情况下选取不同方式即可.
#### async
+ 在html5中，script新增了async的属性，script添加了该属性之后，下载脚本时将可以与页面其他内容并行下载，但是该属性必须在ie9以上的浏览器中才可以使用，并且只能用于加载外部js脚本。
#### defer
+ 在html4中也有一个defer属性，该属性的兼容性更好一点，但是与async一样，可以让js脚本实现异步加载，同样只能用于加载外部js脚本。  
**asyc与defer属性的不同点是**，async会让脚本在加载完可用时立即执行，而defer脚本则会在dom加载完毕后执行，defer脚本的执行会在window.onload之前，其他没有添加defer属性的script标签之后。    
#### 动态创建<script>标签  
```
 <script type="text/javascript">
  function  addScriptTag(src)(){
    var s = document.createElement('script');
    s.type = 'text/javascript';
    s.src = src;
    document.body.appendChild(s);

    })();
  window.onload = function() {
    addScriptTag("/index.js")
  } 
</script>
```  
 ### CSS3动画 
 **animation**（动画）、**transition**（过渡）、transform（变形）  
 + css过渡中的几个属性：
  1. transform的属性值主要包括旋转(rotate)、扭曲(skew)、缩放(scale)和移动(translate)以及矩阵变形(matrix),transform-origin（X,Y）改变基点。
  2. transform:rotate(30deg),2D旋转，正值为顺时针旋转，负值为逆时针旋转，默认旋转基点是中心点。
  3. transform:skew(30deg,10deg),以x轴为轴线逆时针旋转，以y轴为轴线顺时针旋转。基点默认为中心点。另外还有skewX、skewY，分别用来设置单一方向上的扭曲。
  4. transform：scale（2,1.5），表示在水平方向（X轴）缩放2倍，在垂直方向（Y轴）缩放1.5倍。基本默认为中心点。scaleX(<number>) 、scaleY(<number>)用来分别设置单一方向上的缩放。
  5. transform：translate（100px，20px），表示在水平方向上移动100px；在垂直方向上移动20px，y轴向下为正。translateX、translateY值分别设置单一方向上的位移。  
 + transition  transform可以是transition的transition-property的值。
 ```
  div{
    width:100px;
    height:100px;
    background:blue;
    transition:width 2s;
    -moz-transition:width 2s; /* Firefox 4 */
    -webkit-transition:width 2s; /* Safari and Chrome */
    -o-transition:width 2s; /* Opera */
  }
  div:hover{
    width:300px;
  }
 ```
 + animation 动画  
 ```
  div{
  animation: myfirst;
   @keyframes myfirst
  {
  0%   {background: red;}
  25%  {background: yellow;}
  50%  {background: blue;}
  100% {background: green;}
  }
```
```
 不同点：
 transition只作为一种反应过渡到一个CSS属性已经改变了。一个常见的场景是你使用:hover伪类来改变CSS属性的值；触发一个过渡的另一种方法是使用JavaScript以编程方式添加或删除CSS类来模拟一个CSS属性改变。
animation动画则不需要任何显式的触发。一旦你定义动画,它将自动开始播放。
```


  
 css实现动画：animation transition transform
js实现动画: setInterval setTimeout requestAnimationFrame
### JS动画
+ onmouseover onmouseout 
+ setInterval setTimeout

##### 　css动画与js动画
   1.在性能上会稍微好一些，浏览器会对CSS3的动画做一些优化（比如专门新建一个图层用来跑动画）
　　2.代码相对简单
　　但其缺点也很明显：
　　1.在动画控制上不够灵活
　　2.兼容性不好
　　3.部分动画功能无法实现（如滚动动画，视差滚动等）
　　JavaScript的动画正好弥补了这两个缺点，控制能力很强，可以单帧的控制、变换，同时写得好完全可以兼容IE6，并且功能强大。但想想CSS动画的transform矩阵是C++级的计算，必然要比javascript级的计算要快。另外对库的依赖也是一个很让人头疼的问题。
　　所以，对于一些复杂控制的动画，使用javascript会比较靠谱。而在实现一些小的交互动效的时候，就多考虑考虑CSS吧。  
