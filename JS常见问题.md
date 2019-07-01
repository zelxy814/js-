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
 + css中的几个属性：**animation**（动画）、**transition**（过渡）、**transform**（变形）
  1. transform的属性值主要包括旋转(rotate)、扭曲(skew)、缩放(scale)和移动(translate)以及矩阵变形(matrix)
    - transform:rotate(30deg),2D旋转，正值为顺时针旋转，负值为逆时针旋转，默认旋转基点是中心点，也可以通过transform-origin（X,Y）改变基点。
    - transform:skew(30deg,10deg),以x轴为轴线逆时针旋转，以y轴为轴线顺时针旋转。基点默认为中心点。另外还有skewX、skewY，分别用来设置单一方向上的扭曲。可以通过transform-origin（X,Y）改变基点
  
  
  
  
 css实现动画：animation transition transform
js实现动画: setInterval setTimeout requestAnimationFrame
