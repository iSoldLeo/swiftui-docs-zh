--- 来源：https://developer.apple.com/documentation/SwiftUI/WidgetBundleBuilder
抓取时间：2025-12-02T17:49:03Z

---

# WidgetBundleBuilder

**Structure**

用于构建组件包主体的自定义属性。

## 声明

```swift
@resultBuilder struct WidgetBundleBuilder
```

## 概述

使用 `@WidgetBundleBuilder` 属性将组件包中 [body-swift.property](WidgetBundle/body-swift_property.zh-Hans.md) 属性列出的多个组件分组。例如，以下代码定义了一个包含两个组件的组件包。

```swift
@main
struct GameWidgets: WidgetBundle {
   @WidgetBundleBuilder
   var body: some Widget {
       GameStatusWidget()
       CharacterDetailWidget()
   }
}
```

## 组件打包

- **buildBlock()**：从不包含任何语句的代码块（`{ }`）构建一个空组件。

- **buildBlock(_:)**：构建一个以子视图形式编写的单个组件（例如，`{ MyWidget() }`），且不进行任何修改。

- **buildExpression(_:)**：在构建器中构建一个表达式。

- **buildLimitedAvailability(_:)**：在构建器中构建一个可用性检查。

- **buildOptional(_:)**：为多语句闭包中的条件语句生成一个可选组件，该组件仅在条件为真时可见。

## 实现组件包

- **body**：声明应用支持的组件组。

- **Body**：表示组件包内容的组件类型。


---
source: https://developer.apple.com/documentation/SwiftUI/WidgetBundleBuilder
crawled: 2025-12-02T17:49:03Z
---

# WidgetBundleBuilder

**Structure**

A custom attribute that constructs a widget bundle’s body.

## Declaration

```swift
@resultBuilder struct WidgetBundleBuilder
```

## Overview

Use the `@WidgetBundleBuilder` attribute to group multiple widgets listed in the [body-swift.property](WidgetBundle/body-swift_property.zh-Hans.md) property of a widget bundle. For example, the following code defines a widget bundle that consists of two widgets.

```swift
@main
struct GameWidgets: WidgetBundle {
   @WidgetBundleBuilder
   var body: some Widget {
       GameStatusWidget()
       CharacterDetailWidget()
   }
}
```

## Bundling widgets

- **buildBlock()**: Builds an empty Widget from a block containing no statements, `{ }`.
- **buildBlock(_:)**: Builds a single Widget written as a child view (e..g, `{ MyWidget() }`) through unmodified.
- **buildExpression(_:)**: Builds an expression within the builder.
- **buildLimitedAvailability(_:)**: Builds an availability check within the builder
- **buildOptional(_:)**: Produces an optional widget for conditional statements in multi-statement closures that’s only visible when the condition evaluates to true.

## Implementing a widget bundle

- **body**: Declares the group of widgets that an app supports.
- **Body**: The type of widget that represents the content of the bundle.

