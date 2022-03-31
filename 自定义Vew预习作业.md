# 第三次作业

本周作业主要是预习一下下节课我要讲的自定义 View，由于自定义 View 这一块较难，所以只布置一些很简单的预习作业

## 1、预习相关内容

> 请按顺序观看以下博客：
>
> 必看的预习作业（担心你们上课又会起飞），这些算是全网讲得最通俗易懂的博客了
>
> **如果你们已经有部分基础，可以选择性观看**
>
> 1、[Carson带你学Android：自定义View的基础都在这里了！](https://blog.csdn.net/carson_ho/article/details/56009827)
>
> > - 知道 View 的坐标系
> > - View 的 top、left、bottom、right
>
> 2、[Carson带你学Android：深入解析自定义View工作流程](https://carsonho.blog.csdn.net/article/details/98477394)
>
> > - 简单了解下 View 的绘制流程，看不懂没关系
> > - View 和 ViewGroup 的区别
> > - 知道 View 与 ViewGroup 需要重写哪些方法，以及这些方法的可以用来干什么
> > - 查询 `onMeasure()`、`onLayout()`、`onDraw()` 方法的作用
>
> 3、[Carson带你学Android：手把手带你深入学习自定义View Measure过程](https://blog.csdn.net/carson_ho/article/details/56011064)
>
> > **注意：**其中关于 MeasureSpec 他专门放在了这篇文章里面 [Android自定义View：测量规格(MeasureSpec)到底是什么？](https://www.jianshu.com/p/1260a98a09e9)
> >
> > - 理解 Measure 的调用流程
> > - 知道 View 和 ViewGroup 在 Measure 流程中的不同之处
> > - 知道 MeasureSpec 中的三种测量模式
> > - 知道 精确值、match_parent、wrap_content 与 MeasureSpec 的联系
>
> 4、[Carson带你学Android：深入分析自定义View Layout过程](http://blog.csdn.net/carson_ho/article/details/56011112)
>
> > - 理解 Layout 的调用流程
> > - 知道 View 和 ViewGroup 在 Layout 流程中的不同之处
>
> 5、[Carson带你学Android：源码解析自定义View Draw过程](https://blog.csdn.net/carson_ho/article/details/56011153)
>
> > - 理解 Draw 的调用流程
> > - 知道 View 和 ViewGroup 在 Draw 流程中的不同之处
> >
> > Draw 里面需要涉及的东西：
> >
> > > [Carson带你学Android：自定义View Canvas类使用教程](https://carsonho.blog.csdn.net/article/details/60598775)
> > >
> > > [Carson带你学Android：自定义View Path类全面解析](https://www.jianshu.com/p/2c19abde958c)
> > >
> > > **注意：**这个里面有很多 api，这些只需要有个印象就可以了，之后需要的时候才去仔细看
> > >
> > > 你只需要知道以下内容的作用：
> > >
> > > - Canvas
> > > - Paint
> > > - Path
> >
> > 
>
> 6、[Carson带你学Android：手把手教你写一个完整的自定义View](https://carsonho.blog.csdn.net/article/details/62037696)
>
> > 这是他给的一个例子，你们仿照他的来实现一下就可以了
>
> 7、[Android自定义控件三部曲文章索引](https://qijian.blog.csdn.net/article/details/50995268)
>
> > 这是自定义 View 黑书和红书的源文章
> >
> > 这里面有很多高阶的内容，有时间就看看吧

## 2、了解动画

> 动画的知识比较少，这里简单了解以下内容就可以了
>
> 可以看看 [Android自定义控件三部曲文章索引](https://qijian.blog.csdn.net/article/details/50995268) 里面的 《自定义控件三部曲之动画篇》
>
> 如果你对前面的自定义相关内容不是很熟的话，**我建议略过该作业**，之后有时间了，再去系统的学习《View自定义控件开发与实战》这本书
>
> 除了基础的动画以外，还可以了解以下扩展内容：
>
> - Activity、Fragment 的元素共享动画
>
>   > 这个你们自己去找相关内容看吧，这个官方封装了的，直接调 api 就可以实现，只是有些坑，课上再说吧
>   >
>   > 
>   >
>   > 其实元素共享动画是使用下面这两个东西实现的，可以去了解一下
>   >
>   > - Scene
>   > - Transition
>   >
>   > 使用这两个可以自己写一些好看的元素共享动画，这里我给出一个好看的实例
>   >
>   > https://juejin.cn/post/6844903480352604174
>   >
>   > 上面实例的源码地址：https://github.com/DroidsOnRoids/Workcation
>   >
>   > **注意：**由于项目有点古老了，使用了ButterKnife，而且里面还有 Map 模块，所以需要适当修改后再能跑起来，建议新建一个项目然后转移需要的代码，之后课上我会讲解这个实例
>   
> - 其他的一些动画
>
>   > https://blog.csdn.net/qq_29425853/article/details/53104919?utm_medium=distribute.wap_relevant.none-task-blog-2~default~baidujs_title~default-0.essearch_wap_relevant