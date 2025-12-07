---
来源： https://developer.apple.com/documentation/swiftui/view-fundamentals
抓取时间： 2025-12-02T16:01:25Z
---

# 查看基本情况

**API 集合**

使用视图的层次结构来定义应用程序的可视化元素。

## 概览

视图是用于声明应用程序用户界面的构件。每个视图都包含对给定状态下显示内容的描述。用户可看到的应用程序的每个部分都源自视图中的描述，任何符合[View](View.zh-Hans.md) 协议的类型都可以作为应用程序中的视图。



将 SwiftUI 提供的内置视图与在视图的[body-8kl5o](View/body-8kl5o.zh-Hans.md)计算属性中创建的其他自定义视图结合起来，就能组成自定义视图。使用 SwiftUI 提供的视图修改器配置视图，或使用 [ViewModifier](ViewModifier.zh-Hans.md) 协议和 [modifier(_:)](View/modifier.zh-Hans.md) 方法定义自己的视图修改器。

## 创建视图

- 声明自定义视图**：定义视图并将它们组合成视图层次结构。
- **View**：代表应用程序部分用户界面的类型，并提供用于配置视图的修改器。
- **ViewBuilder**：自定义参数属性，用于从闭包构造视图。

## 修改视图

- 配置视图**：通过应用视图修改器来调整视图的特性。
- 减少视图修改器的维护**：将经常重复使用的视图修改器打包到自定义视图修改器中。
- **modifier(_:)**：将修改器应用到视图并返回新视图。
- **ViewModifier**：将修改器应用于视图或其他视图修改器，生成原始值的不同版本。
- **EmptyModifier**：空修饰符或标识修饰符，在开发过程中用于在编译时切换修饰符。
- **ModifiedContent**：应用了修饰符的值。
- **EnvironmentalModifier**：在使用前必须在环境中解析为具体修饰符的修饰符。
- **ManipulableModifier**：修饰语，在使用前必须在环境中解析为具体的修饰语。
- **ManipulableResponderModifier**：修饰语。
- **ManipulableTransformBindingModifier**
- **ManipulationGeometryModifier**
- **ManipulationGestureModifier**
- **ManipulationUsingGestureStateModifier**
- **Manipulable**：各种可操作相关类型的命名空间。

## 响应视图生命周期更新

- **onAppear(perform:)**：在该视图出现之前添加一个要执行的操作。
- **onDisappear(perform:)**：添加要在此视图消失后执行的操作。
- **task(priority:_:)**：添加要在此视图出现前执行的异步任务。
- **task(id:priority:_:)**：添加要在此视图出现前或指定值发生变化时执行的任务。

## 管理视图层次结构

- **id(_:)**：将视图的标识绑定到给定的代理值。
- **tag(_:includeOptional:)**：设置该视图的唯一标记值。
- **equatable()**：当视图的新值与旧值相同时，防止该视图更新其子视图。

## 支持的视图类型

- **AnyView**：基于类型的视图。
- **EmptyView**：不包含任何内容的视图。
- **EquatableView**：不包含任何内容的视图：一种视图类型，它将自己的值与以前的值进行比较，如果新值与旧值相同，就会阻止其子视图更新。
- **SubscriptionView**：通过操作订阅发布者的视图。
- **TupleView**：从 View 值的敏捷元组创建的 View。

## 视图

- 视图配置**：调整层次结构中视图的特征。
- **视图样式**：为不同类型的视图应用内置和自定义外观和行为。
- **Animations**：根据状态变化创建平滑的可视化更新。
- 文本输入和输出**：显示格式化文本并从用户获取文本输入。
- **Images**：为应用程序的用户界面添加图像和符号。
- **控件和指示器**：显示数值并获取用户选择。
- 菜单和命令**：根据上下文访问命令和控件，节省空间。
- **Shapes**：使用颜色、渐变或其他图案对内置和自定义图形进行描边和填充。
- **绘图和图形**：使用图形效果和自定义绘图增强视图效果。


---
source: https://developer.apple.com/documentation/swiftui/view-fundamentals
crawled: 2025-12-02T16:01:25Z
---

# View fundamentals

**API Collection**

Define the visual elements of your app using a hierarchy of views.

## Overview

Views are the building blocks that you use to declare your app’s user interface. Each view contains a description of what to display for a given state. Every bit of your app that’s visible to the user derives from the description in a view, and any type that conforms to the [View](View.zh-Hans.md) protocol can act as a view in your app.



Compose a custom view by combining built-in views that SwiftUI provides with other custom views that you create in your view’s [body-8kl5o](View/body-8kl5o.zh-Hans.md) computed property. Configure views using the view modifiers that SwiftUI provides, or by defining your own view modifiers using the [ViewModifier](ViewModifier.zh-Hans.md) protocol and the [modifier(_:)](View/modifier.zh-Hans.md) method.

## Creating a view

- **Declaring a custom view**: Define views and assemble them into a view hierarchy.
- **View**: A type that represents part of your app’s user interface and provides modifiers that you use to configure views.
- **ViewBuilder**: A custom parameter attribute that constructs views from closures.

## Modifying a view

- **Configuring views**: Adjust the characteristics of a view by applying view modifiers.
- **Reducing view modifier maintenance**: Bundle view modifiers that you regularly reuse into a custom view modifier.
- **modifier(_:)**: Applies a modifier to a view and returns a new view.
- **ViewModifier**: A modifier that you apply to a view or another view modifier, producing a different version of the original value.
- **EmptyModifier**: An empty, or identity, modifier, used during development to switch modifiers at compile time.
- **ModifiedContent**: A value with a modifier applied to it.
- **EnvironmentalModifier**: A modifier that must resolve to a concrete modifier in an environment before use.
- **ManipulableModifier**
- **ManipulableResponderModifier**
- **ManipulableTransformBindingModifier**
- **ManipulationGeometryModifier**
- **ManipulationGestureModifier**
- **ManipulationUsingGestureStateModifier**
- **Manipulable**: A namespace for various manipulable related types.

## Responding to view life cycle updates

- **onAppear(perform:)**: Adds an action to perform before this view appears.
- **onDisappear(perform:)**: Adds an action to perform after this view disappears.
- **task(priority:_:)**: Adds an asynchronous task to perform before this view appears.
- **task(id:priority:_:)**: Adds a task to perform before this view appears or when a specified value changes.

## Managing the view hierarchy

- **id(_:)**: Binds a view’s identity to the given proxy value.
- **tag(_:includeOptional:)**: Sets the unique tag value of this view.
- **equatable()**: Prevents the view from updating its child view when its new value is the same as its old value.

## Supporting view types

- **AnyView**: A type-erased view.
- **EmptyView**: A view that doesn’t contain any content.
- **EquatableView**: A view type that compares itself against its previous value and prevents its child updating if its new value is the same as its old value.
- **SubscriptionView**: A view that subscribes to a publisher with an action.
- **TupleView**: A View created from a swift tuple of View values.

## Views

- **View configuration**: Adjust the characteristics of views in a hierarchy.
- **View styles**: Apply built-in and custom appearances and behaviors to different types of views.
- **Animations**: Create smooth visual updates in response to state changes.
- **Text input and output**: Display formatted text and get text input from the user.
- **Images**: Add images and symbols to your app’s user interface.
- **Controls and indicators**: Display values and get user selections.
- **Menus and commands**: Provide space-efficient, context-dependent access to commands and controls.
- **Shapes**: Trace and fill built-in and custom shapes with a color, gradient, or other pattern.
- **Drawing and graphics**: Enhance your views with graphical effects and customized drawings.

