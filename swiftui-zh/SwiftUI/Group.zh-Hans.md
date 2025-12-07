--- 来源：https://developer.apple.com/documentation/SwiftUI/Group

抓取时间：2025-12-02T16:16:04Z

---

# 组

**Structure**

一种将多个内容类型（例如视图、场景或命令）的实例组合成一个单元的类型。

## 声明

```swift
@frozen struct Group<Content>
```

## 概述

使用组可以将多个视图组合成一个实例，而不会像 [HStack](HStack.zh-Hans.md)、[VStack](VStack.zh-Hans.md) 或 [Section](Section.zh-Hans.md) 那样影响这些视图的布局。创建组后，应用于该组的任何修饰符都会影响该组的所有成员。例如，以下代码将 [headline](font/headline.zh-Hans.md) 字体应用于组中的三个视图。

```swift
Group {
    Text("SwiftUI")
    Text("Combine")
    Text("Swift System")
}
.font(.headline)
```

由于您可以使用 [ViewBuilder](ViewBuilder.zh-Hans.md) 创建视图组，因此可以使用该组的初始化器根据条件语句生成不同类型的视图，并可选择性地为其应用修饰符。以下示例使用 `Group` 添加导航栏标题，无论条件语句生成的视图类型如何：

```swift
Group {
    if isLoggedIn {
        WelcomeView()
    } else {
        LoginView()
    }
}
.navigationBarTitle("Start")
```

修饰符应用于组中的所有成员，而不是组本身。例如，如果您将 [onAppear(perform:)](View/onAppear_perform.zh-Hans.md) 应用于上述组，它将应用于条件语句 `if isLoggedIn` 生成的所有视图，并且每次 `isLoggedIn` 更改时都会执行。

由于视图组本身也是一个视图，因此您可以在其他视图构建器中组合视图组，包括嵌套在其他视图组中。这允许您向不同的视图构建器容器添加大量视图。以下示例使用 `Group` 收集 10 个 [Text](Text.zh-Hans.md) 实例，这意味着垂直堆栈的视图构建器仅返回两个视图——组视图，以及一个额外的 [Text](Text.zh-Hans.md)：

```swift
var body: some View {
    VStack {
        Group {
            Text("1")
            Text("2")
            Text("3")
            Text("4")
            Text("5")
            Text("6")
            Text("7")
            Text("8")
            Text("9")
            Text("10")
        }
        Text("11")
    }
}
```

您可以使用除 [View](View.zh-Hans.md) 之外的多种类型初始化组视图，例如 [Scene](Scene.zh-Hans.md) 和 [ToolbarContent](ToolbarContent.zh-Hans.md)。您提供给组初始化器的闭包使用相应的构建器类型（[SceneBuilder](SceneBuilder.zh-Hans.md)、[ToolbarContentBuilder](ToolbarContentBuilder.zh-Hans.md) 等），并且这些构建器的功能因类型而异。例如，您可以使用分组来返回大量场景或工具栏内容实例，但不能根据条件返回不同的场景或工具栏内容。

## 创建分组

- **init(content:)**：创建一个实例，该实例按顺序组合传入的结果构建器中指定的所有 Rotor 内容，从而生成 Rotor 内容。

## 初始化器

- **init(sections:transform:)**：从给定视图的各个部分构建一个分组。

- **init(subviews:transform:)**：从给定视图的子视图构建一个分组。

## 将视图分组到容器中

- **创建自定义容器视图**：访问各个子视图以组合灵活的容器视图。

- **GroupElementsOfContent**：将给定视图的子视图转换为结果内容视图。

- **GroupSectionsOfContent**：将给定视图的各个部分转换为最终的内容视图。

## 符合以下规范

- AccessibilityRotorContent

- Commands

- Copyable

- CustomizableToolbarContent

- MapContent

- Scene

- TabContent

- TableColumnContent

- TableRowContent

- ToolbarContent

- View


---
source: https://developer.apple.com/documentation/SwiftUI/Group
crawled: 2025-12-02T16:16:04Z
---

# Group

**Structure**

A type that collects multiple instances of a content type — like views, scenes, or commands — into a single unit.

## Declaration

```swift
@frozen struct Group<Content>
```

## Overview

Use a group to collect multiple views into a single instance, without affecting the layout of those views, like an [HStack](HStack.zh-Hans.md), [VStack](VStack.zh-Hans.md), or [Section](Section.zh-Hans.md) would. After creating a group, any modifier you apply to the group affects all of that group’s members. For example, the following code applies the [headline](font/headline.zh-Hans.md) font to three views in a group.

```swift
Group {
    Text("SwiftUI")
    Text("Combine")
    Text("Swift System")
}
.font(.headline)
```

Because you create a group of views with a [ViewBuilder](ViewBuilder.zh-Hans.md), you can use the group’s initializer to produce different kinds of views from a conditional, and then optionally apply modifiers to them. The following example uses a `Group` to add a navigation bar title, regardless of the type of view the conditional produces:

```swift
Group {
    if isLoggedIn {
        WelcomeView()
    } else {
        LoginView()
    }
}
.navigationBarTitle("Start")
```

The modifier applies to all members of the group — and not to the group itself. For example, if you apply [onAppear(perform:)](View/onAppear_perform.zh-Hans.md) to the above group, it applies to all of the views produced by the `if isLoggedIn` conditional, and it executes every time `isLoggedIn` changes.

Because a group of views itself is a view, you can compose a group within other view builders, including nesting within other groups. This allows you to add large numbers of views to different view builder containers. The following example uses a `Group` to collect 10 [Text](Text.zh-Hans.md) instances, meaning that the vertical stack’s view builder returns only two views — the group, plus an additional [Text](Text.zh-Hans.md):

```swift
var body: some View {
    VStack {
        Group {
            Text("1")
            Text("2")
            Text("3")
            Text("4")
            Text("5")
            Text("6")
            Text("7")
            Text("8")
            Text("9")
            Text("10")
        }
        Text("11")
    }
}
```

You can initialize groups with several types other than [View](View.zh-Hans.md), such as [Scene](Scene.zh-Hans.md) and [ToolbarContent](ToolbarContent.zh-Hans.md). The closure you provide to the group initializer uses the corresponding builder type ([SceneBuilder](SceneBuilder.zh-Hans.md), [ToolbarContentBuilder](ToolbarContentBuilder.zh-Hans.md), and so on), and the capabilities of these builders vary between types. For example, you can use groups to return large numbers of scenes or toolbar content instances, but not to return different scenes or toolbar content based on conditionals.

## Creating a group

- **init(content:)**: Creates an instance that generates Rotor content by combining, in order, all the Rotor content specified in the passed-in result builder.

## Initializers

- **init(sections:transform:)**: Constructs a group from the sections of the given view.
- **init(subviews:transform:)**: Constructs a group from the subviews of the given view.

## Grouping views into a container

- **Creating custom container views**: Access individual subviews to compose flexible container views.
- **GroupElementsOfContent**: Transforms the subviews of a given view into a resulting content view.
- **GroupSectionsOfContent**: Transforms the sections of a given view into a resulting content view.

## Conforms To

- AccessibilityRotorContent
- Commands
- Copyable
- CustomizableToolbarContent
- MapContent
- Scene
- TabContent
- TableColumnContent
- TableRowContent
- ToolbarContent
- View

