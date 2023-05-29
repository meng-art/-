### 前端总结

#### 1.nav的设计

  ![202305292335854](https://raw.githubusercontent.com/meng-art/summary/main/202305300009390.png)

```html
<div class="subnav">
              <ul>
                <li><a href="#">前端开发 <span>&gt;</span></a></li>
                <li><a href="#">后端开发</a></li>
                <li><a href="#">移动开发</a></li>
                <li><a href="#">人工智能</a></li>
                <li><a href="#">商业预测</a></li>
                <li><a href="#">云计算&大数据</a></li>
                <li><a href="#">运维&从测试</a></li>
                <li><a href="#">UI设计</a></li>
                <li><a href="#">产品</a></li>
              </ul>
            </div>
```

```css
.subnav ul li {
    height: 45px;
    line-height: 45px;
    padding: 0 20px; 
}
.subnav ul li a span {
    float:right;
}
```

​	首先，为什么那个>号设置在a里，而不是和a并行一起来li里，是因为在css中设置了float: right，那么就会顶着盒子，如果是和a并行，那么会直接顶到边界，这时我们只需要设置li的padding，右侧就会有20px的距离了。

#### 2.嵌套盒子时padding使用易错点

![202305292336315](https://raw.githubusercontent.com/meng-art/summary/main/202305300010129.png)

​	       在goods模块，设计样式是三个大盒子，里面有三个小盒子，但是因为事先设计了版心，且goods模块继承了版心的宽度，如果这个时候“精品推荐”和“修改兴趣”两侧的空隙使用大盒子的padding来设置，就会撑大盒子，所以应该设置h3(第一个盒子)外边距。

#### 三.关于不指定width和height及设置float的注意事项

1. 如果父盒子本身有高度，则不需要清除浮动，但若是没有高度，则需要清除浮动。
2. ==如何盒子本身没有指定width/height属性, 则此时padding不会撑开盒子大小==。
3. margintop对内联元素不起作用，但是内联元素设为float以后，其属性变为块级元素，这个时候margintop对于该内联元素便起作用了。

