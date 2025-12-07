--- 来源：https://developer.apple.com/documentation/SwiftUI/Layout

抓取时间：2025-12-02T16:03:48Z

---

# 布局

**Protocol**

定义视图集合几何形状的类型。

## 声明

```swift
@preconcurrency protocol Layout : Sendable, Animatable
```

## 概述

通常，您可以使用内置的布局容器（例如 [HStack](HStack.zh-Hans.md) 和 [Grid](Grid.zh-Hans.md)）在应用程序的用户界面中排列视图。如果您需要更复杂的布局行为，可以通过创建符合 `Layout` 协议的类型并实现其所需方法来定义自定义布局容器：

- [sizeThatFits(proposal:subviews:cache:)](Layout/sizeThatFits_proposal_subviews_cache.zh-Hans.md) 报告复合布局视图的大小。

- [placeSubviews(in:proposal:subviews:cache:)](Layout/placeSubviews_in_proposal_subviews_cache.zh-Hans.md) 为容器的子视图分配位置。

您只需使用以下两个方法即可定义基本布局类型：

```swift
struct BasicVStack: Layout {
    func sizeThatFits(
        proposal: ProposedViewSize,
        subviews: Subviews,
        cache: inout ()
    ) -> CGSize {
        // Calculate and return the size of the layout container.
    }

    func placeSubviews(
        in bounds: CGRect,
        proposal: ProposedViewSize,
        subviews: Subviews,
        cache: inout ()
    ) {
        // Tell each subview where to appear.
    }
}
```

使用布局的方式与使用内置布局容器相同，只需提供一个 [ViewBuilder](ViewBuilder.zh-Hans.md) 来指定要排列的子视图列表：

```swift
BasicVStack {
    Text("A Subview")
    Text("Another Subview")
}
```

### 支持其他行为

您可以选择实现其他协议方法和属性，以提供更多布局容器功能：

- 通过为每个维度实现 [explicitAlignment(of:in:proposal:subviews:cache:)](Layout/explicitAlignment_of_in_proposal_subviews_cache.zh-Hans.md)，为容器定义显式的水平和垂直布局参考线。

- 通过实现 [spacing(subviews:cache:)](Layout/spacing_subviews_cache.zh-Hans.md)，设置容器周围的首选间距。

- 通过实现 [layoutProperties](Layout/layoutProperties.zh-Hans.md) 静态属性，指示具有堆栈特征的容器的方向轴。

- 通过实现 [makeCache(subviews:)](Layout/makeCache_subviews.zh-Hans.md)，创建并管理一个缓存，用于存储不同布局协议调用中计算出的值。

如果您未实现这些符号，协议会提供默认实现。有关详细信息，请参阅每个方法或属性。

### 添加输入参数

您可以将参数定义为布局的输入，就像您为 [View](View.zh-Hans.md) 所做的那样：

```swift
struct BasicVStack: Layout {
    var alignment: HorizontalAlignment

    // ...
}
```

在实例化布局时设置参数：

```swift
BasicVStack(alignment: .leading) {
    // ...
}
```

如果布局为其参数提供了默认值，则可以在调用处省略参数，但您可能需要保留布局名称后的括号，具体取决于您指定默认值的方式。例如，假设您在参数声明中为基本堆栈设置了默认对齐方式：

```swift
struct BasicVStack: Layout {
    var alignment: HorizontalAlignment = .center

    // ...
}
```

要使用默认居中对齐方式实例化此布局，您无需指定对齐值，但需要添加空括号：

```swift
BasicVStack() {
    // ...
}
```

Swift 编译器在这种情况下需要括号，是因为布局协议实现此调用点语法的方式。具体来说，当您从调用点省略括号时，布局的 [callAsFunction(_:)](Layout/callAsFunction.zh-Hans.md) 方法会查找一个输入参数为零的初始化器。对于没有此类隐式初始化器的布局，您可以通过显式定义一个初始化器来启用更简单的调用点：

```swift
init() {
    self.alignment = .center
}
```

有关 Swift 初始化器的更多信息，请参阅《Swift 程序设计语言》中的 [https://docs.swift.org/swift-book/LanguageGuide/Initialization.html]。

### 通过代理与子视图交互

要执行布局，您需要了解所有子视图的信息，子视图是容器排列的视图。虽然布局无法直接与子视图交互，但它可以通过每个协议方法作为输入参数接收的 [Subviews](Layout/Subviews.zh-Hans.md) 集合访问一组子视图代理。该类型是 [LayoutSubviews](LayoutSubviews.zh-Hans.md) 集合类型的别名，而 [LayoutSubviews](LayoutSubviews.zh-Hans.md) 集合类型又包含 [LayoutSubview](LayoutSubview.zh-Hans.md) 实例，这些实例就是子视图代理。

您可以从每个子视图的代理获取其信息，例如尺寸和间距偏好。这使您可以在确定放置位置之前测量子视图。您还可以通过调用代理的 [place(at:anchor:proposal:)](LayoutSubview/place_at_anchor_proposal.zh-Hans.md) 方法为每个子视图分配位置。在布局的 [placeSubviews(in:proposal:subviews:cache:)](Layout/placeSubviews_in_proposal_subviews_cache.zh-Hans.md) 方法的实现中，对每个子视图调用此方法。

### 访问布局值

视图具有布局值，您可以使用视图修饰符进行设置。布局容器可以根据这些值调整其行为。例如，内置的 [HStack](HStack.zh-Hans.md) 会根据您使用 [layoutPriority(_:)](View/layoutPriority.zh-Hans.md) 视图修饰符设置的优先级，为其子视图分配空间。您的布局容器可以通过读取代理的 [priority](LayoutSubview/priority.zh-Hans.md) 属性来访问子视图的此值。

您还可以通过创建布局键来创建自定义布局值。使用 [layoutValue(key:value:)](View/layoutValue_key_value.zh-Hans.md) 视图修饰符为视图设置值。使用该键作为子视图的索引，从子视图的代理读取相应的值。有关创建、设置和访问自定义布局值的更多信息，请参阅 [LayoutValueKey](LayoutValueKey.zh-Hans.md)。

## 调整容器大小并放置子视图

- **sizeThatFits(proposal:subviews:cache:)**：根据建议大小和子视图数量，返回复合视图的大小。

- **placeSubviews(in:proposal:subviews:cache:)**：为布局的每个子视图分配位置。

- **Layout.Subviews**：布局视图子视图的代理集合。

## 报告布局容器特性

- **explicitAlignment(of:in:proposal:subviews:cache:)**：返回指定水平对齐参考线沿 x 轴的位置。

- **spacing(subviews:cache:)**：返回复合视图的首选间距值。

- **layoutProperties**：布局容器的属性。

## 管理缓存

- **makeCache(subviews:)**：创建并初始化布局实例的缓存。

- **updateCache(_:subviews:)**：当布局发生更改时，更新布局缓存。

- **Cache**：与布局实例关联的缓存值。

## 支持的类型

- **callAsFunction(_:)**：使用自定义布局容器的布局算法，将指定的视图合并为一个复合视图。

## 实例方法

- **depthAlignment(_:)**：设置此布局的深度对齐方式。

- **depthAlignment(_:content:)**：创建具有指定深度对齐方式的布局视图。

## 创建自定义布局容器

- **使用 SwiftUI 组合自定义布局**：使用 SwiftUI 提供的布局工具，在应用程序界面中排列视图。

- **LayoutSubview**：表示布局的一个子视图的代理。

- **LayoutSubviews**：表示布局视图子视图的代理值集合。

## 继承自

- Animatable

- Sendable

- SendableMetatype

## 符合的类型

- AnyLayout

- GridLayout

- HStackLayout

- SpatialContainer

- VStackLayout

- ZStackLayout


---
source: https://developer.apple.com/documentation/SwiftUI/Layout
crawled: 2025-12-02T16:03:48Z
---

# Layout

**Protocol**

A type that defines the geometry of a collection of views.

## Declaration

```swift
@preconcurrency protocol Layout : Sendable, Animatable
```

## Overview

You traditionally arrange views in your app’s user interface using built-in layout containers like [HStack](HStack.zh-Hans.md) and [Grid](Grid.zh-Hans.md). If you need more complex layout behavior, you can define a custom layout container by creating a type that conforms to the `Layout` protocol and implementing its required methods:

- [sizeThatFits(proposal:subviews:cache:)](Layout/sizeThatFits_proposal_subviews_cache.zh-Hans.md) reports the size of the composite layout view.
- [placeSubviews(in:proposal:subviews:cache:)](Layout/placeSubviews_in_proposal_subviews_cache.zh-Hans.md) assigns positions to the container’s subviews.

You can define a basic layout type with only these two methods:

```swift
struct BasicVStack: Layout {
    func sizeThatFits(
        proposal: ProposedViewSize,
        subviews: Subviews,
        cache: inout ()
    ) -> CGSize {
        // Calculate and return the size of the layout container.
    }

    func placeSubviews(
        in bounds: CGRect,
        proposal: ProposedViewSize,
        subviews: Subviews,
        cache: inout ()
    ) {
        // Tell each subview where to appear.
    }
}
```

Use your layout the same way you use a built-in layout container, by providing a [ViewBuilder](ViewBuilder.zh-Hans.md) with the list of subviews to arrange:

```swift
BasicVStack {
    Text("A Subview")
    Text("Another Subview")
}
```

### Support additional behaviors

You can optionally implement other protocol methods and properties to provide more layout container features:

- Define explicit horizontal and vertical layout guides for the container by implementing [explicitAlignment(of:in:proposal:subviews:cache:)](Layout/explicitAlignment_of_in_proposal_subviews_cache.zh-Hans.md) for each dimension.
- Establish the preferred spacing around the container by implementing [spacing(subviews:cache:)](Layout/spacing_subviews_cache.zh-Hans.md).
- Indicate the axis of orientation for a container that has characteristics of a stack by implementing the [layoutProperties](Layout/layoutProperties.zh-Hans.md) static property.
- Create and manage a cache to store computed values across different layout protocol calls by implementing [makeCache(subviews:)](Layout/makeCache_subviews.zh-Hans.md).

The protocol provides default implementations for these symbols if you don’t implement them. See each method or property for details.

### Add input parameters

You can define parameters as inputs to the layout, like you might for a [View](View.zh-Hans.md):

```swift
struct BasicVStack: Layout {
    var alignment: HorizontalAlignment

    // ...
}
```

Set the parameters at the point where you instantiate the layout:

```swift
BasicVStack(alignment: .leading) {
    // ...
}
```

If the layout provides default values for its parameters, you can omit the parameters at the call site, but you might need to keep the parentheses after the name of the layout, depending on how you specify the defaults. For example, suppose you set a default alignment for the basic stack in the parameter declaration:

```swift
struct BasicVStack: Layout {
    var alignment: HorizontalAlignment = .center

    // ...
}
```

To instantiate this layout using the default center alignment, you don’t have to specify the alignment value, but you do need to add empty parentheses:

```swift
BasicVStack() {
    // ...
}
```

The Swift compiler requires the parentheses in this case because of how the layout protocol implements this call site syntax. Specifically, the layout’s [callAsFunction(_:)](Layout/callAsFunction.zh-Hans.md) method looks for an initializer with exactly zero input arguments when you omit the parentheses from the call site. You can enable the simpler call site for a layout that doesn’t have an implicit initializer of this type by explicitly defining one:

```swift
init() {
    self.alignment = .center
}
```

For information about Swift initializers, see [https://docs.swift.org/swift-book/LanguageGuide/Initialization.html] in *The Swift Programming Language*.

### Interact with subviews through their proxies

To perform layout, you need information about all of its subviews, which are the views that your container arranges. While your layout can’t interact directly with its subviews, it can access a set of subview proxies through the [Subviews](Layout/Subviews.zh-Hans.md) collection that each protocol method receives as an input parameter. That type is an alias for the [LayoutSubviews](LayoutSubviews.zh-Hans.md) collection type, which in turn contains [LayoutSubview](LayoutSubview.zh-Hans.md) instances that are the subview proxies.

You can get information about each subview from its proxy, like its dimensions and spacing preferences. This enables you to measure subviews before you commit to placing them. You also assign a position to each subview by calling its proxy’s [place(at:anchor:proposal:)](LayoutSubview/place_at_anchor_proposal.zh-Hans.md) method. Call the method on each subview from within your implementation of the layout’s [placeSubviews(in:proposal:subviews:cache:)](Layout/placeSubviews_in_proposal_subviews_cache.zh-Hans.md) method.

### Access layout values

Views have layout values that you set with view modifiers. Layout containers can choose to condition their behavior accordingly. For example, a built-in [HStack](HStack.zh-Hans.md) allocates space to its subviews based in part on the priorities that you set with the [layoutPriority(_:)](View/layoutPriority.zh-Hans.md) view modifier. Your layout container accesses this value for a subview by reading the proxy’s [priority](LayoutSubview/priority.zh-Hans.md) property.

You can also create custom layout values by creating a layout key. Set a value on a view with the [layoutValue(key:value:)](View/layoutValue_key_value.zh-Hans.md) view modifier. Read the corresponding value from the subview’s proxy using the key as an index on the subview. For more information about creating, setting, and accessing custom layout values, see [LayoutValueKey](LayoutValueKey.zh-Hans.md).

## Sizing the container and placing subviews

- **sizeThatFits(proposal:subviews:cache:)**: Returns the size of the composite view, given a proposed size and the view’s subviews.
- **placeSubviews(in:proposal:subviews:cache:)**: Assigns positions to each of the layout’s subviews.
- **Layout.Subviews**: A collection of proxies for the subviews of a layout view.

## Reporting layout container characteristics

- **explicitAlignment(of:in:proposal:subviews:cache:)**: Returns the position of the specified horizontal alignment guide along the x axis.
- **spacing(subviews:cache:)**: Returns the preferred spacing values of the composite view.
- **layoutProperties**: Properties of a layout container.

## Managing a cache

- **makeCache(subviews:)**: Creates and initializes a cache for a layout instance.
- **updateCache(_:subviews:)**: Updates the layout’s cache when something changes.
- **Cache**: Cached values associated with the layout instance.

## Supporting types

- **callAsFunction(_:)**: Combines the specified views into a single composite view using the layout algorithms of the custom layout container.

## Instance Methods

- **depthAlignment(_:)**: Sets the depth alignment for this layout.
- **depthAlignment(_:content:)**: Creates a layout view with the specified depth alignment.

## Creating a custom layout container

- **Composing custom layouts with SwiftUI**: Arrange views in your app’s interface using layout tools that SwiftUI provides.
- **LayoutSubview**: A proxy that represents one subview of a layout.
- **LayoutSubviews**: A collection of proxy values that represent the subviews of a layout view.

## Inherits From

- Animatable
- Sendable
- SendableMetatype

## Conforming Types

- AnyLayout
- GridLayout
- HStackLayout
- SpatialContainer
- VStackLayout
- ZStackLayout

