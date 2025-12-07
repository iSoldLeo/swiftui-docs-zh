--- 来源：https://developer.apple.com/documentation/SwiftUI/SymbolVariants
抓取时间：2025-12-02T17:35:52Z

---

# SymbolVariants

**Structure**

符号的变体。

## 声明

```swift
struct SymbolVariants
```

## 概述

您可以使用 [Image](Image.zh-Hans.md) 或 [Label](Label.zh-Hans.md) 实例将许多 [doc://com.apple.documentation/design/Human-Interface-Guidelines/sf-symbols] 添加到您的应用中，这些符号都有常见的变体，例如填充版本或包含在圆圈内的版本。符号名称指示其变体：

```swift
VStack(alignment: .leading) {
    Label("Default", systemImage: "heart")
    Label("Fill", systemImage: "heart.fill")
    Label("Circle", systemImage: "heart.circle")
    Label("Circle Fill", systemImage: "heart.circle.fill")
}
```

您可以使用 `SymbolVariants` 配置视图层级结构的一部分，使其所有符号及其子视图中的符号都使用特定的变体。将 [symbolVariant(_:)](View/symbolVariant.zh-Hans.md) 修饰符添加到视图，即可为该视图的环境设置变体。例如，您可以使用此修饰符创建与上述示例相同的标签集，只需在标签声明中使用符号的基本名称：

```swift
VStack(alignment: .leading) {
    Label("Default", systemImage: "heart")
    Label("Fill", systemImage: "heart")
        .symbolVariant(.fill)
    Label("Circle", systemImage: "heart")
        .symbolVariant(.circle)
    Label("Circle Fill", systemImage: "heart")
        .symbolVariant(.circle.fill)
}
```

或者，您可以通过将 [symbolVariants](EnvironmentValues/symbolVariants.zh-Hans.md) 环境值传递给 [environment(_:_:)](View/environment.zh-Hans.md) 修饰符，直接在环境中设置变体：

```swift
Label("Fill", systemImage: "heart")
    .environment(\.symbolVariants, .fill)
```

SwiftUI 会在某些环境中为您设置变体。例如，SwiftUI 会自动为出现在 [swipeActions(edge:allowsFullSwipe:content:)](View/swipeActions_edge_allowsFullSwipe_content.zh-Hans.md) 方法的 `content` 闭包中的项目，或作为 [TabView](TabView.zh-Hans.md) 标签栏项目的项目应用 [fill-swift.type.property](SymbolVariants/fill-swift_type_property.zh-Hans.md) 符号变体。

## 获取符号变体

- **none**：符号没有变体。

- **circle**：将符号封装在圆形中的变体。

- **square**：将符号封装在正方形中的变体。

- **rectangle**：将符号封装在矩形中的变体。

- **fill**：填充符号的变体。

- **slash**：在符号上画一条斜线的变体。

## 修改变体

- **circle**：用圆圈包裹的变体版本。

- **square**：用正方形包裹的变体版本。

- **rectangle**：用矩形包裹的变体版本。

- **fill**：填充后的变体版本。

- **slash**：带斜线的变体版本。

## 比较变体

- **contains(_:)**：返回一个布尔值，指示当前变体是否包含指定的变体。

## 设置符号变体

- **symbolVariant(_:)**：使视图中的符号显示特定变体。

- **symbolVariants**：此环境中要使用的符号变体。

## 符合以下标准

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/SymbolVariants
crawled: 2025-12-02T17:35:52Z
---

# SymbolVariants

**Structure**

A variant of a symbol.

## Declaration

```swift
struct SymbolVariants
```

## Overview

Many of the [doc://com.apple.documentation/design/Human-Interface-Guidelines/sf-symbols] that you can add to your app using an [Image](Image.zh-Hans.md) or a [Label](Label.zh-Hans.md) instance have common variants, like a filled version or a version that’s contained within a circle. The symbol’s name indicates the variant:

```swift
VStack(alignment: .leading) {
    Label("Default", systemImage: "heart")
    Label("Fill", systemImage: "heart.fill")
    Label("Circle", systemImage: "heart.circle")
    Label("Circle Fill", systemImage: "heart.circle.fill")
}
```



You can configure a part of your view hierarchy to use a particular variant for all symbols in that view and its child views using `SymbolVariants`. Add the [symbolVariant(_:)](View/symbolVariant.zh-Hans.md) modifier to a view to set a variant for that view’s environment. For example, you can use the modifier to create the same set of labels as in the example above, using only the base name of the symbol in the label declarations:

```swift
VStack(alignment: .leading) {
    Label("Default", systemImage: "heart")
    Label("Fill", systemImage: "heart")
        .symbolVariant(.fill)
    Label("Circle", systemImage: "heart")
        .symbolVariant(.circle)
    Label("Circle Fill", systemImage: "heart")
        .symbolVariant(.circle.fill)
}
```

Alternatively, you can set the variant in the environment directly by passing the [symbolVariants](EnvironmentValues/symbolVariants.zh-Hans.md) environment value to the [environment(_:_:)](View/environment.zh-Hans.md) modifier:

```swift
Label("Fill", systemImage: "heart")
    .environment(\.symbolVariants, .fill)
```

SwiftUI sets a variant for you in some environments. For example, SwiftUI automatically applies the [fill-swift.type.property](SymbolVariants/fill-swift_type_property.zh-Hans.md) symbol variant for items that appear in the `content` closure of the [swipeActions(edge:allowsFullSwipe:content:)](View/swipeActions_edge_allowsFullSwipe_content.zh-Hans.md) method, or as the tab bar items of a [TabView](TabView.zh-Hans.md).

## Getting symbol variants

- **none**: No variant for a symbol.
- **circle**: A variant that encapsulates the symbol in a circle.
- **square**: A variant that encapsulates the symbol in a square.
- **rectangle**: A variant that encapsulates the symbol in a rectangle.
- **fill**: A variant that fills the symbol.
- **slash**: A variant that draws a slash through the symbol.

## Modifying a variant

- **circle**: A version of the variant that’s encapsulated in a circle.
- **square**: A version of the variant that’s encapsulated in a square.
- **rectangle**: A version of the variant that’s encapsulated in a rectangle.
- **fill**: A filled version of the variant.
- **slash**: A slashed version of the variant.

## Comparing variants

- **contains(_:)**: Returns a Boolean value that indicates whether the current variant contains the specified variant.

## Setting a symbol variant

- **symbolVariant(_:)**: Makes symbols within the view show a particular variant.
- **symbolVariants**: The symbol variant to use in this environment.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

