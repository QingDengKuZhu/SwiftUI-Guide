# SwiftUI-Guide
![image](https://github.com/fzhlee/SwiftUI-Guide/blob/master/images/swiftui-logo.png)<br/>
图片来源：developer.apple.com
<br/><br/>
**SwiftUI<br/>
更好的应用，更少的代码。<br/>
SwiftUI是一种创新、简单的iOS开发中的界面布局方案，可以通过Swift语言的强大功能，在所有的Apple平台上快速构建用户界面。 仅使用一组工具和API为任何Apple设备构建用户界面。 <br/>
SwiftUI具有易于阅读和自然编写的声明式Swift语法，可与新的Xcode设计工具无缝协作，使您的代码和设计完美同步。 <br/>
自动支持动态类型、暗黑模式、本地化和可访问性，意味着您的第一行SwiftUI代码已经是您编写过的最强大的UI代码了（太煽情了~）。**
<br/>

---

<br/>
SwiftUI的80节教程及源码<br/>
所有课程基于Xcode 11 beta5，并在Xcode 11 beta5上编译通过。<br/>
当Xcode11正式版发布之后，会更新所有源码，以适配Xcode 11正式版。<br/>
<br/>
iOS开发相关互动课程列表，手把手学习iOS开发，App Store免费下载：<br/>
1、互动教程合集：https://apps.apple.com/cn/app/id1392811165<br/>
2、Xcode互动教程免费下载地址：https://itunes.apple.com/cn/app/id1063100471<br/>
3、Swift语言入门实例互动教程免费下载地址：https://itunes.apple.com/cn/app/id1320746678<br/>
4、app开发中的神兵利器免费下载地址：https://itunes.apple.com/cn/app/id1209739676<br/>
5、Objective-C语言应用开发互动教程免费下载地址：https://apps.apple.com/cn/app/id838877136<br/>
<br/>

---


![image](https://github.com/fzhlee/SwiftUI-Guide/blob/master/images/SwiftUI.png)
<br/>
图片来源：developer.apple.com<br/>

## 示例导航区：

* <span id="Image_D">Chapter 1: 常用的Views</span>
	- [1FirstProject](#1FirstProject)
	- [2Text-BasicStyle](#2Text-BasicStyle)
	- [3Text-Paragraph](#3Text-Paragraph)
	- [4Text-Padding](#4Text-Padding)
	- [5Text-FullScreen](#5Text-FullScreen)
	- [6Text-DateFormatter](#6Text-DateFormatter)
	- [7Text-Append](#7Text-Append)
	- [8TextField](#8TextField)
	- [9TextField-SecureField](#9TextField-SecureField)
	- [10Button](#10Button)
	- [11Button-sheet](#11Button-sheet)
	- [12Spacer](#12Spacer)
	- [13Divider](#13Divider)
	- [14Image-Basic](#14Image-Basic)
	- [15Image-Style](#15Image-Style)
	- [16Image-Processing](#16Image-Processing)
	- [17Image-Blend](#17Image-Blend)
	- [18Image-Mask](#18Image-Mask)
	- [19Image-Transform](#19Image-Transform)
	- [20Image-Web](#20Image-Web)
	- [21Picker](#21Picker)
	- [22PickerDate](#22PickerDate)
	- [23Slider](#23Slider)
	- [24Stepper](#24Stepper)
	- [25Segment](#25Segment)
	- [26Toggle](#26Toggle)
	- [27TabView](#27TabView)
	- [28Webview](#28Webview)
	- [29MapView](#29MapView)
	- [30Shape-Circle](#30Shape-Circle)
	- [31Shape-Rectangle](#31Shape-Rectangle)
	- [32Shape-Path](#32Shape-Path)
	- [33GradientLinear](#33GradientLinear)
	- [34GradientAngular](#34GradientAngular)
	- [35GradientRadial](#35GradientRadial)
	<br/>

* <span id="Image_D">Chapter 2: Animation动画</span>
	- [1scaleEffect+default](#1scaleEffect+default)
	- [2Opacity+linear](#2Opacity+linear)
	
# 第一章 常用控件Controls<br/>
<h4 id="1FirstProject"> 第一节：SwiftUI空白项目的创建步骤：<h4>
1、打开Xcode，然后使用菜单命令:File > New > Project命令，打开项目创建窗口。<br/>
2、在项目模板选择窗口中，选择Single View App模板，然后点击Next按钮，进入下一步设置窗口。<br/>
3、在项目配置窗口中，需要勾选Use SwiftUI复选框，然后填写其它的配置选项，点击Next按钮，完成项目的创建。<br/>
4、SwiftUI项目创建完成之后，其项目结构和代码功能如下图所示：<br/>
	
![image](https://github.com/fzhlee/SwiftUI-Guide/blob/master/images/SwiftUIXcode.png) 

<br/>
5、项目导航区：<br/>

<table>
	<thead>
		<tr>
			<th>文件名称</th>
			<th>说明</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>AppDelegate.swift</td>
			<td>提供didFinishLaunchingWithOptions等方法，用来处理程序启动之后的事件，或者响应来自外部的事件。</td>
		</tr>
		<tr>
			<td>SceneDelegate.swift</td>
			<td>设置应用程序窗口的rootViewController，并指定使用哪个ContentView作为rootViewController的rootView。</td>
		</tr>
		<tr>
			<td>ContentView.swift</td>
			<td>项目的初始界面，用户界面上的可视控件可以放置在此文件中。</td>
		</tr>
		<tr>
			<td>Assets.xcassets</td>
			<td>项目的资源文件，您可以在此处放置项目中所需的图片、颜色等资源。</td>
		</tr>
		<tr>
			<td>LaunchScreen.storyboard</td>
			<td>用来配置项目启动过程中所显示的内容。</td>
		</tr>
		<tr>
			<td>Info.plist</td>
			<td>项目的配置属性文件，配置产品名称、版本号、Build号、Bundle Identifier等项目。</td>
		</tr>
	</tbody>
</table>

6、代码编辑器：<br/>
<ul>
  <li>SwiftUI使用声明性语法，因此开发者可以简单地说明用户界面应该做什么。</li>
  <li>例如，您可以编写需要包含文本字段的项目列表，然后描述每个字段的对齐方式，字体和颜色。</li>
  <li>您的代码比以前更简单，更易于阅读，从而节省您的时间和维护。</li>
</ul>
<br/>
7、ContentView.swift代码说明：<br/>

```swift
//导入SwiftUI框架
import SwiftUI 		             

//定义一个名为ContentView的结构体，该结构体遵循View协议，遵循View协议的元素才可以在SwiftUI框架中。就像在UIKit中，所见皆UIView一样，在SwiftUI中，所见皆是View。
struct ContentView: View {		 
//添加View协议中的body属性，在body属性中通过SwiftUI提供的各种布局控件，完成界面元素的搭建。关键词some表示返回的是某种View，但是SwiftUI不需要在意是具体的哪种View
    var body: some View {
    	//在屏幕上显示一个标签，标签的内容位于双引号之内
        Text("Hello World")
    }
}

//当处于Debug模式时，允许执行下方的代码
#if DEBUG
//定义一个遵循PreviewProvider的结构体，用于设置在右侧预览区需要实时预览的内容
struct ContentView_Previews: PreviewProvider {
//添加PreviewProvider协议中的previews属性，用来设置在实时预览区显示的内容
    static var previews: some View {
    	//设置在实时预览区显示ContentView结构体中的内容，您还可以在此设置预览的模拟器尺寸、是否Dark Mode等选项。
        ContentView()
    }
}
#endif
```

8、SceneDelegate.swift代码说明：<br/>

```swift
//使用此方法可以选择性地配置UIWindow窗口，并将其附加到提供的UIWindowScene
func scene(_ scene: UIScene, willConnectTo session: UISceneSession, options connectionOptions: UIScene.ConnectionOptions) {

        if let windowScene = scene as? UIWindowScene {
	    //初始化一个UIWindow窗口对象
            let window = UIWindow(windowScene: windowScene)
	    // 使用一个UIHostingController实例，作为该窗口的根 view controller
            window.rootViewController = UIHostingController(rootView: ContentView())
	    // 将新建的窗口作为当前程序的窗口对象
            self.window = window
	    // 将窗口作为主窗口并显示
            window.makeKeyAndVisible()
        }
    }
```
<h4 id="2Text-BasicStyle"> 第二节：Text-BasicStyle： </h4>
Text类似于UIKit中的UILabel，用于显示一行或多行的文字内容。<br/>
示例代码：<br/>

```swift
VStack{
    //Basic style
    Text("www.hdjc8.com")
	.bold()

    Text("www.hdjc8.com")
	.italic()

    Text("www.hdjc8.com")
	.underline()

    Text("www.hdjc8.com")
	.underline(true, color: .orange)

    Text("www.hdjc8.com")
	.strikethrough()

    Text("www.hdjc8.com")
	.strikethrough(true, color: .orange)

    Text("www.hdjc8.com")
	.foregroundColor(Color.orange)

    Text("www.hdjc8.com")
	.baselineOffset(CGFloat(5.0))
	.background(Color.orange)

     Text("www.hdjc8.com")
	 .background(Image("Picture"), alignment: .bottom)

    //Font
    VStack{
	Text("www.hdjc8.com")
	    .font(.footnote)

	Text("www.hdjc8.com")
	    .font(.system(size: 36))

	Text("www.hdjc8.com")
	    .font(.system(.title, design: .monospaced))

	Text("www.hdjc8.com")
	    .font(.custom("BradleyHandITCTT-Bold", size: 36))

	Text("www.hdjc8.com")
	    .fontWeight(Font.Weight.heavy)

	Text("www.hdjc8.com")
	    .fontWeight(Font.Weight.ultraLight)

    }
}
```

<details close>
  <summary>View running results</summary>
<img width="100%" src="images/2Text-BasicStyle.png"/>
</details>
