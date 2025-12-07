---
来源： https://developer.apple.com/documentation/SwiftUI/AnyLayout
抓取时间： 2025-12-02T17:39:24Z
---

# AnyLayout

**Structure**

布局协议的类型抹除实例。

## 声明

```swift
@frozen struct AnyLayout
```

## 概览

使用`AnyLayout` 实例可以动态更改布局容器的类型，而不会破坏子视图的状态。例如，您可以创建一个布局，根据当前的动态类型设置在水平和垂直布局之间切换：

```swift
struct DynamicLayoutExample: View {
    @Environment(\.dynamicTypeSize) var dynamicTypeSize

    var body: some View {
        let layout = dynamicTypeSize <= .medium ?
            AnyLayout(HStackLayout()) : AnyLayout(VStackLayout())

        layout {
            Text("First label")
            Text("Second label")
        }
    }
}
```

与 `AnyLayout` 一起使用的类型必须符合 [Layout](Layout.zh-Hans.md) 协议。上例在 [HStackLayout](HStackLayout.zh-Hans.md) 和 [VStackLayout](VStackLayout.zh-Hans.md) 类型之间进行了选择，这两种类型是符合协议的内置 [HStack](HStack.zh-Hans.md) 和 [VStack](VStack.zh-Hans.md) 容器的版本。您也可以使用自己定义的自定义布局类型。

## 创建布局

- **init(_:)**：创建一个封装指定布局的类型迭代值。

## 在布局类型间转换

- **HStackLayout**：水平容器，可用于条件布局。
- **VStackLayout**：垂直容器，可在条件布局中使用。
- **ZStackLayout**：可以在条件布局中使用的覆盖容器。
- **GridLayout**：可以在条件布局中使用的网格。

## 符合

- 动画
- 布局
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/AnyLayout
crawled: 2025-12-02T17:39:24Z
---

# AnyLayout

**Structure**

A type-erased instance of the layout protocol.

## Declaration

```swift
@frozen struct AnyLayout
```

## Overview

Use an `AnyLayout` instance to enable dynamically changing the type of a layout container without destroying the state of the subviews. For example, you can create a layout that changes between horizontal and vertical layouts based on the current Dynamic Type setting:

```swift
struct DynamicLayoutExample: View {
    @Environment(\.dynamicTypeSize) var dynamicTypeSize

    var body: some View {
        let layout = dynamicTypeSize <= .medium ?
            AnyLayout(HStackLayout()) : AnyLayout(VStackLayout())

        layout {
            Text("First label")
            Text("Second label")
        }
    }
}
```

The types that you use with `AnyLayout` must conform to the [Layout](Layout.zh-Hans.md) protocol. The above example chooses between the [HStackLayout](HStackLayout.zh-Hans.md) and [VStackLayout](VStackLayout.zh-Hans.md) types, which are versions of the built-in [HStack](HStack.zh-Hans.md) and [VStack](VStack.zh-Hans.md) containers that conform to the protocol. You can also use custom layout types that you define.

## Creating the layout

- **init(_:)**: Creates a type-erased value that wraps the specified layout.

## Transitioning between layout types

- **HStackLayout**: A horizontal container that you can use in conditional layouts.
- **VStackLayout**: A vertical container that you can use in conditional layouts.
- **ZStackLayout**: An overlaying container that you can use in conditional layouts.
- **GridLayout**: A grid that you can use in conditional layouts.

## Conforms To

- Animatable
- Layout
- Sendable
- SendableMetatype

