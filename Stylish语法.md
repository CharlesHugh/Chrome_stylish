stylish语法


1.".<classname>":指定名为classname的class
2."div[id="idname"]":指定id名为idname的div


替换网页标签中图片:
使用CSS可以轻松替换背景图片，但替换<img>标签创建的图像时则需要执行以下技巧来切换图像。
#your-selector-here {
    height: 0 !important;
    width: 0 !important;
    /* these numbers match the new image's dimensions */
    padding-left: 125px !important;
    padding-top: 25px !important;
    background: url(http://example.com/your/image/here) no-repeat !important;
}
选取网页特定元素
示例1:
<table id="prices">
    <tbody>
        <tr>
            <td>Hamburger</td>
            <td>$5.00</td>
        </tr>
        <tr>
            <td>Hot dog</td>
            <td>$4.00</td>
        </tr>
        <tr>
            <td>Taco</td>
            <td>$5.25</td>
        </tr>
    </tbody>
</table>

选取prices中所有第二个td标签:
#prices td:nth-child(2)

示例2:
<div class="container">
    <p>Paragraph one</p>
    <p>Paragraph two</p>
    <p>Maybe the number of paragraphs changes per page.</p>
    <p style="float: right">A floating aside on the page.</p>
    <p>More paragraphs...</p>
</div>

隐藏float标签:
.container p[style="float: right"] {
    display: none !important;
}

进阶:
1.[#id], [.class]可以用来合并使用相同声明的规则
2..class1.class2可以用来匹配.class1 class2这种元素
3.DIV[style="%"] （%代表元素属性）形式可以用来匹配无 id 无 class 但有特殊样式（不至于轨道炮）的元素
4.DIV[id^=%] DIV[class^=%]可以用来匹配以%开头的元素
5.DIV[%1]:nth-child(1)>DIV[%2]:nth-child(2) （第一个%1声明的div元素内的第二个%2声明的div元素）可以用同级元素顺序及上下级元素从属来匹配元素
6.opacity 属性是个很赞的声明，设定合适的透明度有助于大幅提升浏览体验
7.div[%1] { opacity: 0 } div[%1]:hover { opacity: 1 }可以实现元素淡出鼠标悬停时才显示的效果
8.页面中的iframe需要针对其原始url（而非当前页面）写选择器


