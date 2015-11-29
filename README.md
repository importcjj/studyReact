### 相关说明

本人学习React是动手写的一些小demo，方便理解概念和用法。其中的大部分demo参考了网络上一些大牛或是相关书籍代码，并且同时也加上了自己的一些改动吧。欢迎阅读参考，如有错误之处，敬请指出~

> 不定期更新

### 学习积累

- 2015年11月22日18:54:52

发现一： 自定义组件的名字好像首字母必须大写！

发现二： 自定义组件标签 名字与闭合斜杠之间空一格；

发现三： 自定义组件的render函数只能返回一个定义元素，不能是一组元素；

发现四： props用于在组件树中传递数据和配置。props在组件内部应该是只读的！

发现五： state只存在于组件内部，自定义组件应该通过setState修改其state，每当修改state时，都会重新调用render方法；

<br />

- 2015年11月23日10:46:22

发现一：通过refs获取组件树中带有ref属性的DOM节点，必须在虚拟DOM渲染之后(componentDidMount之后)；

发现二： 通过refs获取真实DOM节点时，ref属性的值必须是唯一；

发现三： 通过refs获取真实DOM节点时，写不写.getDOMNode()好像都能获取成功；

<br />

- 2015年11月24日16:30:59

发现一：尽管refs很强大，但是可能会成为React在性能上的障碍；

<br />

- 2015年11月24日15:35:58

发现一： 无约束组件的值不受react控制，可使用ref属性取真实DOM节点。 相反，约束组件的值往往通过state 被react所掌控，可在事件处理函数中使用event.target来获取该DOM节点。

<br />

2015年11月28日13:30:09

发现一： 组件嵌套是垂直方向（代码封装），而mixin则是通用部分的横向抽离（代码复用）；

发现二：父子组件如何通信？父组件通过属性传递给子组件，其中可包括事件处理函数，子组件绑定后触发事件时可向父组件传递消息，这种方式称为委托；

发现三： bind方法(类似python的偏函数)可用来给事件处理函数设置默认值，bind方法的第一参数通常传this，用来指代组件本身；之后的参数依次对应该事件处理函数的参数；设置完成后，会返回一个新函数；通常使用在逻辑相同，但需要判断事件来源的情况；

发现四： js中函数套函数，内层函数中的this会丢失，无法访问外层函数所指向的对象，一般会指向一个全局变量，需在外层函数通过新的变量将this保存下来后，在内层访问该新变量；

2015年11月28日22:06:19

发现一： { }中可以使用求值表达式（调用函数也可以），但不能使用普通js语句，例如 if 等等，使用三元表达式代替；

发现二： class属性用className代替， for属性使用htmlFor代替；

发现三： 注释有单行注释/**/和多行注释//

发现四：css的使用，可以定义一个style对象，css属性使用驼峰式，可直接将style对象通过组件style的属性，react可正确处理；

发现五：react定义了三个非标准DOM属性: 1⃣️dangerouslySetInnerHTML =>在JSX中动态插入HTML   2⃣️ref => 父组件可通过refs.xxx来获取渲染后的带有ref=“xxx”属性的子组件   3⃣️key；

2015年11月29日16:33:39

发现一： 不管一个组件产生了多少个实例， 他的getDefaultProps方法只会被调用一次，就是在组件声明的时候（createClass），之后的实例均会共享；

生命周期中的钩子方法

发现二： 初始阶段 getDefaultProps -> getInitialState -> componentWillMount -> render -> componentDidMount

发现三： 运行中阶段 componentWillReceiveProps -> shouldComponentUpdate -> componentWillUpdate -> render -> componentDidUpdate

发现四： 销毁阶段 componentWiilUnmount

发现五： 使用React.unmountComponentAtNode(mountNode)可删除一个组件

![](http://imgchr.com/images/7479D8B0-4A32-4C2A-BA17-3D290415212E.png)



![](http://imgchr.com/images/A4FA1AF2-85CD-44BA-83FC-E17DF820617F.png)

![](http://imgchr.com/images/718CD7B7-A7B5-4F94-A5D0-1DC271D5EF88.png)

2015年11月29日17:39:37

发现一： 用户自定义事件处理方法命名规范（驼峰式） handle+事件名，例如 handleClick, handleMouseover等等；

js事件列表

触摸(移动端)

1. onTouchCancel
2. onTouchEnd
3. onTouchMove
4. onTouchStart

键盘

1. onKeyDown
2. onKeyPress
3. onKeyUp

剪切(支持不好)

1. onCopy
2. onCut
3. onPaste

表单

1. onChange
2. onInput
3. onSubmit(可以用来阻止默认表单提交事件)

焦点

1. onFocus
2. onBlur （失去焦点）

UI元素

1. onScroll

鼠标滚轮滚动(使用不多)

1. onWheel

鼠标

1. onClick 单击
2. onContextMenu 右键菜单
3. onDoubleClick
4. onMouseDown
5. onMouseEnter
6. onMouseLeave
7. onMouseMove
8. onMouseOut
9. onMouseOver
10. ononMouseUp

拖拽

1. onDrop
2. onDrag
3. onDragEnd
4. onDragEnter
5. onDragExit
6. onDragLeave
7. onDragOver
8. onDragStart

发现二：时间处理函数接受得event对象并不是原生的event对象，而是经过react封装过的；

