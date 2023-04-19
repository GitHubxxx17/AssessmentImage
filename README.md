# 二评
## 陈铭师妹你好：很高兴收到你的考核！

### 本次考核的优点：
1. 完成绝大部分基本要求
2. 完成大部分加分项
3. 使用`flex`布局
4. 视频可播放
5. 总结文档详细，代码有注释
 
### 不足：
>1. 没有用overflow隐藏超出的部分
![](https://githubxxx17.github.io/AssessmentImage/cmBug01.png)
2. 动画有些生硬，不建议用定时器做动画，师妹你可以用css的transition配合js做动画，利用js直接改变元素的left即可实现流畅的动画
3. 按钮动画太快，当滑动区域到最左端或最右端也没有改变按钮的状态
- 按钮动画应该改成这样
```css
@keyframes arrowhead_l {
    /*左边按钮的动画*/
    0% {
        transform: translateX(0) rotate(-90deg);
        /*先平移再旋转*/
        opacity: 1;
    }

    50% {
        transform: translateX(-100%) rotate(-90deg);
        opacity: 0;
    }

    51% {
        transform: translateX(100%) rotate(-90deg);
        opacity: 0;
    }

    100% {
        transform: translateX(0) rotate(-90deg);
        opacity: 1;
    }
}
```
- 改变按钮的鼠标样式可以用css的`cursor`,比如要禁止点击样式是`cursor:no-drop;`

>flex布局那一部分做得还不错，但有一个小细节，就是鼠标移入元素后，如果是“查看案例”的字样应该改变鼠标样式

>右边导航栏的动画还是有些问题,部分样式没有改变
![](https://githubxxx17.github.io/AssessmentImage/cmBug02.png)
1. 应该是鼠标移入父元素出现动画，移入子元素是不出现动画的，这部分内容我觉得用js实现比较好，在鼠标移出父元素时让子元素进行动画，动画结束后隐藏子元素（可用定时器实现），这样移入子元素的区域就不会出现动画了，因为用`opacity`改变的是子元素的透明度，实际上子元素还一直在那个位置，没有被隐藏，要用`display:none;`才能真正隐藏子元素。
2. 动画在缩放的时候是靠右缩放的，所有要用`transform-origin: right center;`设置元素的基点位置在右边中间的位置
3. 鼠标移入后应该改变父元素的背景颜色的svg的颜色，要用css改变svg的颜色需要把svg的代码直接放在html里面，然后就可以通过css改变svg的fill属性来改变颜色。

>其余版块的问题由其他师姐解答

### 对总结文档中一些问题的解答及建议
1. `.a hover .b`是控制子元素的样式，如果想控制同级元素的样式需要这样写`.a hover +.b`
2. 媒体查询是不难的，第三次考核会考察到这个知识点，师妹有时间的话可以去了解一下
3. 对于页面的一些比较难获取或找不到的图标，可以在<a href="https://www.iconfont.cn/home/index">iconfont-阿里巴巴矢量图标库</a>上找，不用一模一样的，长得像一点就行
4. css可以拆开来写，一个版块对应一个css文件，这样就不用在一个css文件里面写几千行代码了，也方便找bug，如果js比较多的话也可以拆开来写
5. 


### 评语