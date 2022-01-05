# Android_Learning_Route
 21级学弟的Android学习清单

# 寒假学习路线

> 按照传统，寒假考核不能使用非官方库，所以以下内容不包含第三方库
>
> 难度：kotlin < 框架 < 自定义View

## 1、kotlin

> 可以买《第一行代码》第三版进行学习，上面附带讲解了 `kotlin` 的使用
>
> **注意：** kotlin 并不是寒假必须学习的内容，寒假仍能使用 java 来写。在下学期开学会给你们几周的时间来学习（自学，我们不会教），所以可以跳过先学下面的

## 2、框架相关

> 框架方面比较深奥难懂，建议去GitHub上搜索 wanAndroid 项目阅读一下别人写的源码，不然光看博客的解释不动手操作是很难理解框架的使用的

### 2.1、MVP

> 虽然后期Android开发都是使用的MVVM，但MVVM是MVP的演化版，MVP还是值得去看一看的

### 2.2、MVVM

> Android官方推荐架构，需要与 `LiveData`、`ViewModel` 配合使用

#### 2.2.1、ViewModel

#### 2.2.2、LiveData

> 寒假期间搞清楚怎么用即可，主要是配合MVVM中的网络层进行回调

#### 2.2.3、DataBinding

> 目前 `DataBinding` 有一些奇怪的bug，我们一般把他当成了 `ViewBinding` 在用

## 3、自定义View与滑动冲突

> 自定义 View 方面比较难且耗时间，如果你有想实现的一些复杂控件，可以来看看这一块

### 3.1、自定义View

> 点击跳转[自定义View](#2.4、自定义View)

### 3.2、滑动冲突

> 滑动冲突是设计自定义View必会的
>
> 点击跳转[滑动冲突](#2.5、滑动冲突)

## 4、自己撸后端（不推荐）

> 不是很推荐，光是 Android 的知识你都学不完，当然，卷王除外



# 大一下及以后学习路线

> 东西有些多，其实学长我们好多都没学过😂

## 1、必须内容

### 1.1、kotlin

### 1.2、四大主件

> 除掉 `ContenProvder` 可不用学习
>
> ### Activity
>
> ### Service
>
> ### Broadcast

### 1.3、Rxjava的使用

### 1.4、Retrofit的使用

> ### 与Rxjava配套使用
>
> ### 与协程配套使用
>
> > 由于目前掌邮不能使用协程，主要是与阿里的热修护 `hotfix` 有关（三年了，不知道新版本能用了不）

### 1.5、Room的使用

> ### 与Rxjava配套使用
>
> ### 与协程配套使用
>
> > 由于目前掌邮不能使用协程，主要是与阿里的热修护 `hotfix` 有关（三年了，不知道新版本能用了不）

### 1.6、MVVM + ViewModel + LiveData + DataBinding + Retrofit + Rxjava + Room

> 这是掌邮目前的框架，市面上的大部分应用应该都是类似于这样设计的
>
> 以下是对于 Android 之后发展的推测（仅代表个人观点）：
>
> `Rxjava` 以后会被 `协程` 代替
>
> `LiveData` 以后会被 `Flow` 代替
>
> `XML View` 与 `Compose` 以后应该会共存（个人认为各有各的优势）
>
> 还有现在谷歌开始推荐 `MVI` 架构了（靠，谷歌真的是要累死我们开发者）



## 2、扩展内容

> 学长们不讲或讲不细的自学内容

### 2.1、Material Design

> 这里面很多便捷的控件及用法，比如：`TabLayout` 直接添加小圆点、共享元素动画等
>
> 推荐直接看官网：https://material.io/
>
> 推荐去打包他的源码：https://github.com/material-components/material-components-android（虽然源码没写注释，但想实现某个功能时可以去看看是否已经有实现了的）

### 2.2、线程池

> ### 阻塞队列
>
> > 使用LinedList实现阻塞队列
>
> ### 仿写CacheThreadPool等java自带的几个线程池

### 2.3、RecyclerView高阶用法

> ### 1、点击事件不要写在onBindViewHolder中
>
> ### 2、实现侧滑删除、长按移动Item（这些官方都有封装好的接口）
>
> ### 3、notifyItemChanged ( position：Int, paylosd：Any? )
>
> > 这是**两个形参**的刷新，后面有一个单独的参数 `paylosd: Any?`
> >
> > 该方法与 `onBindViewHolder(holder, position, payloads)` 三个参数的回调有关系
> >
> > > **补充内容**
> > >
> > > 刷新时图片 rv 的图片会闪动
> > >
> > > 该问题与 rv 的缓存有关，因为在刷新时这个 `ViewHolder` 与缓存中进行了互换，相当于重新加载了图片
> > >
> > > 解决办法：调用带有 `paylosd` 参数的刷新，取消与缓存的互换
> >
> >
>
> ### 4、差分刷新 DiffUtil
>
> > DiffUtil 中也有一个可重写的方法，其中带有 `paylosd` 参数
> >
> > **注：** 网上部分博客的差分比较有些问题，尽量自己搞懂原理（不是算法原理，而是究竟该比较什么数据才会是真正的差分，尤其是 `areItemsTheSame` 方法）

### 2.4、自定义View

> 推荐：
>
> 入门：《Android自定义控件开发入门与实战》
>
> 进阶：《Android自定义控件高阶进阶与精彩实例》
>
> 博客：[自定义View源码原理](https://blog.csdn.net/carson_ho/article/details/56009827)
>
> ### 1、onLayout
>
> ### 2、onMearsure
>
> ### 3、onDraw
>
> ### 4、动画
>
> ### 你需要知道的其他知识：
>
> > ### View.post/postdelay()方法
> >
> > ### 如何在activity得到控件的宽和高
>
> ### 可以做的实例
>
> > - 流式布局

### 2.5、滑动冲突

> ### 普通滑动
>
> > 推荐：
> >
> > 博客：  
> > [图解事件分发](https://www.jianshu.com/p/e99b5e8bd67b)  
> > [dispatchTouchEvent源码解析](https://blog.csdn.net/u011637339/article/details/50427156?utm_medium=distribute.wap_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromBaidu%7Edefault-1.essearch_wap_relevant&depth_1-utm_source=distribute.wap_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromBaidu%7Edefault-1.essearch_wap_relevant)
> >
> > 图片：[郭祥瑞的滑动分发分支图](https://www.processon.com/view/link/6191f797079129330ada2bd7)
> >
> > ### dispatchTouchEvent
> >
> > ### onInterceptTouchEvent
> >
> > ### onTouchEvent
> >
> > ### requestDisallowInterceptTouchEvent
>
> ### 嵌套滑动
>
> > 推荐：
> >
> > 博客：[图解嵌套滑动](https://blog.csdn.net/hongxue8888/article/details/104022221)
> >
> > ### NestedScrollingParent和NestedScrollingParent2
> > > [NestedScrollingChild2官方文档](https://developer.android.com/reference/androidx/core/view/NestedScrollingChild2)
> >
> > ### NestedScrollingChild和NestedScrollingChild2
> > > [NestedScrollingParent2官方文档](https://developer.android.com/reference/androidx/core/view/NestedScrollingParent2)
> >
> > > 题外话：为什么还要看1，不直接看2？因为部分官方控件中只使用了1，所以你要知道1和2的区别。还有一个3，这个3在网上的教程较少，直接继承了2，是2的一个简化版。
> > > [NestedScrollingParent3官方文档](https://developer.android.google.cn/reference/androidx/core/view/NestedScrollingParent3?hl=en)
>
> ### 与设计多层自定义View时的使用
>
> > 建议自己写一些复杂自定义View，包含单击、滑动等一系列事件
> >
> > 可参考郭祥瑞写的 [TimeSelectView](https://github.com/985892345/TimeSelectView_Library) 控件(按照 README导入简单使用一下，源码写的很拉，在重写了😫，这里直接给出软件下载地址，下载后自己试着想想该怎么设计: https://wwi.lanzouo.com/iC1JGy08a0h
>
> ### 简单看看View和ViewGroup中滑动源码
>
> ### 可以做的实例
>
> > - 下拉刷新（可参考 `SmartRefreshLayout`，也可以把上拉加载一起实现）

### 2.6、协调者布局CoordinatorLayout

> 学习它需要知道嵌套滑动
>
> ### 高阶用法自定义 Behavior

### 2.7、仿写Glide

> 1、实现三级缓存
>
> 2、搞懂它为什么能根据 View 的生命周期而自动取消加载图片（他可没有使用 `Lifecycle` 这个东西）
>
> 3、改用 `Lifecycle` 实现

### 2.8、仿写Okhttp

> 尝试实现拦截器
>
> **仿写Gson**

### 2.9、仿写Rxjava

### 2.10、仿写EventBus

> 但不建议使用，此框架因过于灵活，会像goto一样造成滥用而难以溯源

### 2.11、MotionLayout

> 有很多自定义View难实现时用这个来写很简单
>
> 推荐谷歌官网：https://developer.android.google.cn/training/constraint-layout/motionlayout/examples?hl=zh_cn



## 3、其他内容

> 学习成本过高或目前阶段不够或目前不使用

### 3.1、设计模式

> 有几个**简单的**还是自己要**提前了解**下

### 3.2、协程原理

> 目前掌邮不能用协程，你们可以在自己写的项目中使用

### 3.3、Navigation

> 目前还有些坑，官方还在改进中，掌邮中也不使用

### 3.4、RecyclerView

> ### 滑动事件源码
>
> ### LayoutManger
>
> ### 多级缓存

### 3.5、paging3

> 不是2和1

### 3.6、使用注解实现一些骚操作

### 3.7、gradle的使用

### 3.8、hilt依赖注入

### 3.9、jvm

### 3.10、Compose

### 3.11、Flow —— LiveData的替代者

### 3.xx 别卷了，别卷了！

### ......


