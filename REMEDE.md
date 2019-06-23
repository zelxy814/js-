## 获取行间样式与非行间样式
## 获取行间样式
- Ele.style.width; ele.style[‘width’]; 只要能用方括号表示的都能用点表示。除非形式参数只能用方括号表示。
- Style只能取行内样式的属性值，带单位，但是可以设置行内样式或非行内样式的属性值。
- currenStyle可以取行内样式和非行内样式的值，带单位，重复的话取优先级最高的，只能取不能设置属性值，只兼容IE。
- getComputeredStyle可以取行内样式和非行内样式的值，带单位，重复的话取优先级最高的，只能取不能设置属性值，兼容火狐chrome浏览器。
```
if(ele.currentStyle){
		console.log(ele.currentStyle[styleName]);
}
else{
console.log(getComputedStyle(ele,null)[styleName]);
}
```
（1）.offsetwidth属性返回值涵盖元素的width+border+padding。  
（2）.style.width属性返回值仅包含元素的width属性值。  
（3）.offsetwidth属性返回值是数字，不带单位，style.width返回值带有单位。  
（4）.style.width属性是可读写的。  
（5）.offsetwidth只读属性，不能赋值。  
- getAttribute(属性名)只能获取写在行内的样式名的值，如id，name，style等
