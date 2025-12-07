---
来源： https://developer.apple.com/documentation/swiftui/viewbuilder
抓取时间： 2025-12-03T19:22:21Z
---

# ViewBuilder

**Structure**

自定义参数属性，用于从闭包构造视图。

### 声明

```swift
@resultBuilder struct ViewBuilder
```

## 概览

您通常会将[ViewBuilder](ViewBuilder.zh-Hans.md) 用作产生子视图的闭包参数属性，从而允许这些闭包提供多个子视图。例如，下面的`contextMenu` 函数接受通过视图生成器生成一个或多个视图的闭包。

```swift
func contextMenu<MenuItems: View>(
    @ViewBuilder menuItems: () -> MenuItems
) -> some View
```

该函数的客户端可以使用多语句闭包提供多个子视图，如下例所示：

```swift
myView.contextMenu {
    Text("Cut")
    Text("Copy")
    Text("Paste")
    if isSymbol {
        Text("Jump to Definition")
    }
}
```

## 构建内容

- **buildBlock()**：从一个不包含任何语句的代码块构建一个空视图。
- **buildBlock(_:)**：将作为子视图写入的单个视图原封不动地通过。
- **buildExpression(_:)**：在构建器中构建表达式。

## 有条件地构建内容

- **buildEither(first:)**：当条件为真时，为多语句闭包中的条件语句生成内容。
- **buildEither(second:)**：当条件为假时，为多语句闭包中的条件语句生成内容。
- **buildIf(_:)**：为多语句闭包中的条件语句生成一个可选视图，该视图仅在条件求值为 true 时可见。
- **buildLimitedAvailability(_:)**：处理执行可用性检查的条件编译器控制语句的视图内容。

## 创建视图

- **声明自定义视图**：定义视图并将它们组合成视图层次结构。
- **View**：一种代表应用程序部分用户界面的类型，并提供用于配置视图的修改器。


---
source: https://developer.apple.com/documentation/swiftui/viewbuilder
crawled: 2025-12-03T19:22:21Z
---

# ViewBuilder

**Structure**

A custom parameter attribute that constructs views from closures.

## Declaration

```swift
@resultBuilder struct ViewBuilder
```

## Overview

You typically use [ViewBuilder](ViewBuilder.zh-Hans.md) as a parameter attribute for child view-producing closure parameters, allowing those closures to provide multiple child views. For example, the following `contextMenu` function accepts a closure that produces one or more views via the view builder.

```swift
func contextMenu<MenuItems: View>(
    @ViewBuilder menuItems: () -> MenuItems
) -> some View
```

Clients of this function can use multiple-statement closures to provide several child views, as shown in the following example:

```swift
myView.contextMenu {
    Text("Cut")
    Text("Copy")
    Text("Paste")
    if isSymbol {
        Text("Jump to Definition")
    }
}
```

## Building content

- **buildBlock()**: Builds an empty view from a block containing no statements.
- **buildBlock(_:)**: Passes a single view written as a child view through unmodified.
- **buildExpression(_:)**: Builds an expression within the builder.

## Conditionally building content

- **buildEither(first:)**: Produces content for a conditional statement in a multi-statement closure when the condition is true.
- **buildEither(second:)**: Produces content for a conditional statement in a multi-statement closure when the condition is false.
- **buildIf(_:)**: Produces an optional view for conditional statements in multi-statement closures that’s only visible when the condition evaluates to true.
- **buildLimitedAvailability(_:)**: Processes view content for a conditional compiler-control statement that performs an availability check.

## Creating a view

- **Declaring a custom view**: Define views and assemble them into a view hierarchy.
- **View**: A type that represents part of your app’s user interface and provides modifiers that you use to configure views.

