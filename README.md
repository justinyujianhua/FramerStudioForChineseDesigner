Framer Studio 文档中文翻译
=============================================================================

作为近期一个凸显逼格的交互设计工具，近期开始学习他的使用方式，考虑到framer中文网翻译停止的情况，我决定自己开始该文档的翻译工作。计划为期半年。


Print（打印输出）
------------------------------------------------------------------------
你可以在检查变量时运行打印输出命令。他的工作方式类似console.log,只有当使用打印输出命令时，输出才会直接显示在你的原型中。需要注意的是，你需要在Javascript中使用print()命令（但不是在CoffeeScript中）我们会忽略这些说明在之后的文档中


	print "Hello"
	\# Output: "Hello"
	\# 你可以用他检查任何类型的值，当然也可以同时检查多个类型的值

	layerA = new Layer({x:20, name:"Hi"})
	\# A single property value

	print layerA.x
	\# Output: 20
	\# Multiple values

	print layerA.x, print layerA.opacity, layerA.name

	\# Output: 20, 1.0, "Hi"





Defaults(默认)
------------------------------------------------------------------------
Framer默认缺省值允许你在创建模板时，覆盖层和动画的默认属性（译者按：创建时，会给你的层和动画一个默认的值）
例如：所有的新创建的层都会有一个可见的淡蓝色的背景颜色。这些颜色都是可以被覆盖替换的


	\# Override the default background color for layers
	\# 给这个层替换背景颜色
	Framer.Defaults.Layer.backgroundColor = "red"

	\# Override the default corner radius for layers
	\# 给这个层替换默认圆角
	Framer.Defaults.Layer.borderRadius = 10
	layerA = new Layer()
	print layerA.backgroundColor
	\# Output: "red"
	print layerA.borderRadius
	\# Output: 10



这里有个例子可以设置默认动画曲线。请注意，这也将用于layer.states开关除非你重写他们的那层layer.states.animationoptions。


	\# Override the default animation options for all Animations
	\# 对所有的动画重写这个默认的动画选项
	Framer.Defaults.Animation = {
	    curve: "spring(100,10,0)"
	}

	\# Override the default corner radius for layers
	\# 对层重写这个默认的圆角
	Framer.Defaults.Layer.borderRadius = 10

	layerA = new Layer()
	layerA.animate({
	    properties: {x:100}

	})

\# The animation will now use the "spring(100,10,0)" curve

\# 这个动画现在将使用spring(100,10,0)这个曲线


