# 复合样式

``` css
    border: 1px solid #999
```

``` css
.board-row::after {
    clear: both;
    content: "";
    display: block;
}
```

> 清除浮动，在board-row后面插入一个内容为空的块元素，块元素两边不能有浮动，确保他会被显示在所有浮动元素之后
