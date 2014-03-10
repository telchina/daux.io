> Caffeinated（音[ˈkæfɪneɪtɪd]），中文读音类似“忾菲内梯德”。英文直译为：含有咖啡因的。因此**Caffeinated JS**可以译做**含有咖啡因的JS框架**。取此名意在带给开发者令人兴奋的开发体验。
> <span style="text-align:right;display:block">——作者注</span>

大概4年前，我在开发Web应用时开始使用大量的jQuery插件和Ajax来增强用户体验。随着代码量不断扩大，一些弊端开始显现出来。由于jQuery插件使用时要求必须针对某个元素进行操作，因此DOM声明相关的代码跟Javascript脚本基本是分开的。页面中充斥着大量被拆分的代码。而且这些代码还相当的冗余。虽然jQuery插件能提升用户的体验但是对于传统的JSTL<!--或者Flex-->开发者来说，这无疑是自找麻烦。

举例说来，一般的jQuery插件使用形如下面的这段代码：

```
	......
	
	<div id="btn1" class="button">登录</div>

	<script>
		$("#btn1").button({
			color			: "primary"
			, size			: "large"
			, data-toggle	: "modal"
			, data-target	: "#modal1"
			})
	</script>

	......

```

在这段冗长啰嗦的代码中其实有效的信息无非寥寥几行：

```
button({
	color			: "primary"
	, label			: "登录"
	, size			: "large"
	, data-toggle	: "modal"
	, data-target	: "#modal1"
})
```

这其实完全可以用一行很简单的代码来代替：

```
<button color="primary" size="large" data-toggle="modal" data-target="#modal1">登录<button>
```

以上三段代码，从功能的角度讲他们实现的是完全一样的功能。但是从代码书写的简易程度、可读性上来说最后一种更加受到开发者欢迎。从这一点出发，我决定开发一个Web应用的UI开发框架来帮助开发者实现这种简单的UI编程方式。其技术目标主要有两点：

1. 广泛的集成第三方的jQuery控件库。<br/> 作为UI开发框架，丰富的控件库是必不可少的。但是除非有很强大的商业开发支持，否则完善的UI控件库短时间内很难建立。为了在控件库方面达到足以抗衡商业产品的水平，我希望借助广泛的jQuery插件社区的力量来达到这一目标。因此能够广泛、良好的支持第三方jQuery插件是首要设计目标。
2. 尽可能减少开发者编写的代码量。<br/>在这一点上，任何希望取得大家认可的开发框架都会设此目标。我也不例外。

除了上面所述外，Caffeinated JS还添加了其他一些Web UI开发的使用功能。更多细节请继续参考Caffeinated JS架构简述。

<!--## 为什么一定要基于jQuery插件来建立UI控件库？-->

