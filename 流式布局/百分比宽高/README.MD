# 关于流式布局中的百分比宽高问题
## 1.margin & padding
如果将元素的margin、padding值设置为百分比，那么它们都是相对其父元素的宽度而言的。
## 2.width & height
width设置为百分比，它的值由父元素宽度决定。
height设置百分比，它的值有父元素的高度决定。若父元素没有设置高度，则子元素的百分比高度是无效的。
### 利用以上两个知识点，我们可以在流式布局中写出一个正方形。
如`index.html`和`style.css`所示<br>
1. `box`为最外层，指定了*width*<br>
2. `circle`的*width*为100%，与`box`的宽度相同，*height*为0，`padding-bottom:100%,`使得*padding-bottom*与`box`的*width*相等。<br>
3. `img`则设置了`width:100%;height:100%;`，欲使其与`circle`的宽高相等得到正方形，但此时的*height*是为0的。<br>
4. **只有为`circle`设置了position:relative; 为`img`设置了position:absolute; 才可以得到想要的效果**
