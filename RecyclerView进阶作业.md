# 第二次作业

本次作业主要是预习 RV 的一些用法

## 1、onBindViewHolder

> - 简单了解为什么一个 Item 的点击事件不能写在 onBindViewHolder 回调里面
>   - 这个涉及到 RV 的底层原理，可以看看群文件里面的性能优化那篇文章（那篇文章就是兮神写的，看懂了下节课就可以不用来了 :）
>
> 点击事件的正确写法应该是写在 ViewHolder 中，通过 ViewHolder#getLayoutPosition() 或者 ViewHolder#getAbsoluteAdapterPosition() 来获取 item 当前位置
>
> **该作业可以在下面的作业中体现**

## 2、RV 的基本使用

### 2.1、RV 实现侧滑删除

> 有以下集中侧滑删除效果：
>
> - 效果一：侧滑到一定位置显示一个删除按钮，然后点击删除（图片来之网络）
>
> <img src="https://img-blog.csdn.net/20180531174932775?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2RhcGFuZ3phbw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70" style="float: left;" />
>
> - 效果二：直接侧滑然后全部删除，不显示删除按钮（图片来之网络）
>
> <img src="https://upload-images.jianshu.io/upload_images/9124992-49caa75246eaeeff.gif?imageMogr2/auto-orient/strip|imageView2/2/w/365/format/webp" style="zoom:80%;float:left" />
>
> **效果一更推荐使用重写子 View 来实现，比如重写 ScrollView**
>
> **效果二更推荐使用 ItemTouchHelper 来实现，而且官方封装的很彻底，几行代码就能实现**
>
> > 效果一也是可以使用 ItemTouchHelper，但有些坑，不推荐，因为官方把 ItemTouchHelper 封装的过于彻底了些，有些东西不好去实现
>
> 

### 2.2、RV 实现长按移动，交换 item 位置

> 使用 ItemTouchHelper 可以快捷实现
>
> 任务：实现以下功能（图片来之网络）
>
> <img src="https://img-blog.csdn.net/20170717182505351?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvWkFDSF9aSE9V/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast" style="float: left;" />

### 2.3、RV 加分割线

> 一般情况下都是在 Item 的布局中添加一条额外的线来模拟分割线
>
> 但这种添加会使最后一个 item 也有分割线
>
> 所以该作业让你们学习一下：**ItemDecoration**
>
> 可以看看这篇文章：https://blog.csdn.net/harvic880925/article/details/82959754?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522164707677816780265491745%2522%252C%2522scm%2522%253A%252220140713.130102334.pc%255Fblog.%2522%257D&request_id=164707677816780265491745&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~blog~first_rank_ecpm_v1~rank_v31_ecpm-2-82959754.nonecase&utm_term=RecyclerView&spm=1018.2226.3001.4450

### 2.4、以上三个可以结合在一起使用

> 这里给个例子：（图片来之网络）
>
>     <img src="https://img-blog.csdnimg.cn/img_convert/b9bef71f9aca5642c27d55c429db8d2c.gif" style="zoom: 67%; float: left;" />
>
> >**有没有卷王来写个这个？**（图片来之网络）
> >
> > <img src="https://img-blog.csdn.net/20181009150453441?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2hhcnZpYzg4MDkyNQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70" style="zoom:80%;float:left" />
> >
> >把 长按移动、侧滑删除、添加分割线 三个作业一起满足，且长按移动还可以改变 item 的级数（比如从第三级变为第一级），就像一个手机软件 滴答清单 的任务长按把任务改为子任务一样
> >
> >**该作业不强制要求，因为实现的话会很耗时间**

## 3、ConcatAdapter

> 这个是官方为了解决 ViewHolder 过多而提出的解决方案
>
> **任务：写个 demo 学习一下**

## 4、DiffUtil 差分刷新

> 看看这篇文章：https://blog.csdn.net/zxt0601/article/details/52562770
>
> ### SortedList
>
> > 给你们布置作业才发现有这个东西，在 [RV 官网](https://developer.android.google.cn/reference/androidx/recyclerview/widget/RecyclerView?hl=en)的介绍中发现的
> >
> > 官方文档：https://developer.android.google.cn/reference/androidx/recyclerview/widget/SortedList
> >
> > CSDN一些例子：https://so.csdn.net/so/search?q=RecyclerView%20SortedList&t=&u=&urw=
> >
> > 感觉例子有点少，我梳理了一下：
> >
> > - 一般我们给 Adapter 数据传的是 ArrayList，现在可以用这个 SortedList 来代替 
> > - 主要用法是配合 SortedListAdapterCallback 类来绑定 Adapter 实现自动差分刷新
> > - 或者实现 SortedList.Callback 来自定义一些刷新的监听
>
> **任务：写个 demo 学习一下**
>
> 差分这东西会用就行，不用去了解差分算法的实现
>
> ### 差分的坑
>
> > 其实使用差分刷新，那么在 `onBindViewHolder()` 中的 `position` 有个坑，
> >
> > 可以看看这篇文章：https://blog.csdn.net/weixin_28318011/article/details/112872952
> >
> > 原因在于：
> >
> > 使用差分后 `onBindViewHolder()` 不会被重新调用，那么可能存在有 View 还保留着上次的 `position`，而与实际位置就会有偏差
> >
> > 解决方案：
> >
> > 使用 ViewHolder#getLayoutPosition() 或者 ViewHolder#getAbsoluteAdapterPosition() 来延迟获取位置
>
> 

## 5、ListAdapter

> 这是官方专门封装了异步差分刷新的 Adapter
>
> **注意：**是 `androidx.recyclerview.widget` 包下的 ListAdapter，不是 `android.widget` 包下的
>
> **任务：写个 demo 学习一下**

## 6、Paging3

> 官方专门的 RV 分页解决方案，建议配合协程自己写写，网络数据的话可以使用 wanAndroid 的
>
> **任务：写个 demo 学习一下**

## 7、notifyItemChanged ( position：Int, paylosd：Any? )

> 这是**两个形参**的刷新，后面有一个单独的参数 `paylosd: Any?`
>
> - 该方法与 `onBindViewHolder(holder, position, payloads)` 三个参数的回调有关系
> - 也与差分刷新中 `public Object getChangePayload(int oldItemPosition, int newItemPosition)` 这个方法也有关系
> - 如果想直接获取 RV 中某个 item 的实例，可采用这种方法。具体做法是刷新时 `paylosd` 传入一个回调，然后在 `onBindViewHolder(holder, position, payloads)` 中得到 `payloads`，进行类型判断，然后进行回调
>
> 这个方法设计到了 RV 的底层原理，不用过于探究为什么，可以知道他与单个参数 `notifyItemChanged(position：Int)` 方法的不同之处

## 8、notifyDataSetChanged() 导致图片闪动

> 为什么会闪动（这里的闪动有两种，一种透明度的改变是动画，一种瞬间的白闪是图片被重绘）：
>
> - ViewHolder 进行了互换，在互换时会默认**调用动画**，如果是同一张图片会感觉是闪动
> - **图片被重新添加**上了 View，如果图片较大，重绘就会出现瞬间白闪
>
> 解决方案：
>
> - 从动画入手，取消它的动画
>
>   ```kotlin
>   val animator = recyclerView.itemAnimator
>   if (animator != null) {
>       animator.addDuration = 0 // 修改 ViewHolder 被添加时的动画时间
>       animator.removeDuration = 0 // 修改 ViewHolder 被删除时的动画时间
>   }
>   // 缺点，虽然不闪了，但在图片较大时出现第二种闪动，原因：1、ViewHolder被互换；2、图片被重新添加到 View 上
>   ```
>
> - 从 ViewHolder 入手，取消它的互换
>
>   ```kotlin
>   // 先调用：
>   mAdapter.setHasStableIds(true)
>   // 再重写 Adapter 的这个方法：
>   override fun getItemId(position: Int): Long {
>       return position 
>   }
>   /*
>   * 这样设置会使在调用刷新时，ViewHolder 并不会与缓存进行交换，这样确实可以解决图片闪动问题，
>   * 
>   * 缺点：只是干掉了 ViewHolder 的交换，图片仍然需要被重新添加到 View 上
>   * */
>   ```
>
> - **使用差分刷新**
>
>   不再使用 `notifyDataSetChanged()` 而该用差分刷新，就能很好地解决 ViewHolder 互换和图片闪动的问题
>
> **这不算作业，但这是必须要知道的东西**

# 不要求作业：

## 1、认识一下 `Adapter#setHasStableIds()` 和 `Adapter#getItemId()`

> - 有什么用？
> - 一般用于什么时候？

## 2、ItemTouchHelper 的实现原理

> 这个有些难度，有时间可以去看看
>
> 我的课表代码就参考了这个东西，基本原理是 RV 写了一个用于监听事件的方法，然后 ItemTouchHelper 通过监听事件来实现长按移动和侧滑这些

## 3、RV 的 LayoutManger

> 这个难度过高，不适合你们当前阶段学习
>
> https://so.csdn.net/so/search?q=RecyclerView&t=blog&u=harvic880925

## 4、RV 的缓存机制

> 这个难度过高，不适合你们当前阶段学习

## 5、RV的其他

> 建议阅读《Android自定义控件高级进阶与精彩实例》中的 RV 部分，
>
> > 这里也有该书大佬的 CSDN 文章：https://blog.csdn.net/harvic880925/article/details/50995268，
> >
> > 这是 RV 部分：https://so.csdn.net/so/search?q=RecyclerView&t=blog&u=harvic880925
>
> 强烈建议多去看看官网
>
> > https://developer.android.google.cn/reference/androidx/recyclerview/widget/RecyclerView?hl=en
> >
> > 官网有很多可以学习的
> >
> > 比如离开或者进入屏幕时的回调等，这些官网都有 [api 介绍](https://developer.android.google.cn/reference/androidx/recyclerview/widget/RecyclerView.Adapter?hl=en#onViewDetachedFromWindow(VH))
> >
> > 

## 6、很好看的刷新控件

> 一个第三方库的刷新控件：https://github.com/scwang90/SmartRefreshLayout
>
> 你们可以接入来使用下，以后开发属于自己的软件也可以使 ui 变得更好看些

# 作业截止时间：3月19日，即下周六







