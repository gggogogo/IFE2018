## 3D相比2D 新增详解

### perspective
`perspective: number | none`属性值为数字，该属性是设置透视点的距离，学过透视的应该很容易理解，没学过的可以简单搜必应了解一下，也可以想象存在一个参考点，这个点距离你浏览器画面的距离就是这个数值，透视点可以让你的页面产生3d效果，**需要注意的是这个数值是设置在父容器上的，毕竟是参考点。**

### perspective-origin

属性值为`left | right | 百分数值` 作用是设定透视点的平面位置，居中还是其他定位点。同perspective配合使用产生3D效果。**也是定义在父容器上的。**

### backface-visibility

当元素不面向屏幕时候是否可见，值为 `visible | hiddem` ,假如你将两个盒子重叠放置，然后使用3D变换，设定了`backface-visibility: hiddem`后翻转过去不面对屏幕的元素将不可见。

### transform-style

属性值为`flat | preserve-3d` ,flat是不保留子元素3D属性，preserve-3d则是保留

**这个相当重要啊！！!**,就这个NO.4来举个栗子，如果你将两张图片放在了同一个盒子里面，然后设定了父容器翻转，然后你会发现并没有3D翻转，而仅仅是2D翻转，也就是父容器只是在二维层，面上将两张图叠加了，然后在翻转也只是镜像翻转。只有两张图叠加可能感受不了，但是如果多张图片，并且这些图片有3D位移的话就有区别了。**所以如果你的父容器没有出现3D效果请试试记得加上这个属性！**