--- 来源：https://developer.apple.com/documentation/SwiftUI/DisclosureGroupStyle
抓取时间：2025-12-02T17:33:25Z

---

# DisclosureGroupStyle

**Protocol**

一种用于指定视图层级结构中披露组的外观和交互方式的类型。

## 声明

```swift
@MainActor @preconcurrency protocol DisclosureGroupStyle
```

## 概述

要配置视图层级结构的披露组样式，请使用 [disclosureGroupStyle(_:)](View/disclosureGroupStyle.zh-Hans.md) 修饰符。

要创建自定义披露组样式，请声明一个符合 `DisclosureGroupStyle` 的类型。实现 [makeBody(configuration:)](DisclosureGroupStyle/makeBody_configuration.zh-Hans.md) 方法，以返回一个视图，该视图由 SwiftUI 提供给该方法的 `configuration` 元素组成。

```swift
struct MyDisclosureStyle: DisclosureGroupStyle {
    func makeBody(configuration: Configuration) -> some View {
        VStack {
            Button {
                withAnimation {
                    configuration.isExpanded.toggle()
                }
            } label: {
                HStack(alignment: .firstTextBaseline) {
                    configuration.label
                    Spacer()
                    Text(configuration.isExpanded ? "hide" : "show")
                        .foregroundColor(.accentColor)
                        .font(.caption.lowercaseSmallCaps())
                        .animation(nil, value: configuration.isExpanded)
                }
                .contentShape(Rectangle())
            }
            .buttonStyle(.plain)
            if configuration.isExpanded {
                configuration.content
            }
        }
    }
}
```

如果类型的基本声明中包含符合性声明，则符合此协议的类型将继承协议的隔离性：`@preconcurrency @MainActor`

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

默认情况下，隔离到主要参与者，但这不是必需的。要在扩展中声明符合性声明以选择退出主要参与者隔离：

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## 获取样式

- **automatic**：披露组样式，可根据当前上下文自动解析其外观。

## 创建自定义披露组样式

- **makeBody(configuration:)**：创建表示披露组主体的视图。

- **DisclosureGroupStyleConfiguration**：披露组实例的属性。

- **DisclosureGroupStyle.Configuration**：披露组实例的属性。

- **Body**：表示披露组主体的视图。

## 支持的类型

- **AutomaticDisclosureGroupStyle**：一种披露组样式，可根据当前上下文自动解析其外观。

## 设置集合视图的样式

- **listStyle(_:)**：设置此视图中列表的样式。

- **ListStyle**：描述列表行为和外观的协议。

- **tableStyle(_:)**：设置此视图中表格的样式。

- **TableStyle**：一种将自定义外观应用于视图中所有表格的类型。

- **TableStyleConfiguration**：表格的属性。

- **disclosureGroupStyle(_:)**：设置此视图中披露组的样式。

## 符合规范的类型

- AutomaticDisclosureGroupStyle


---
source: https://developer.apple.com/documentation/SwiftUI/DisclosureGroupStyle
crawled: 2025-12-02T17:33:25Z
---

# DisclosureGroupStyle

**Protocol**

A type that specifies the appearance and interaction of disclosure groups within a view hierarchy.

## Declaration

```swift
@MainActor @preconcurrency protocol DisclosureGroupStyle
```

## Overview

To configure the disclosure group style for a view hierarchy, use the [disclosureGroupStyle(_:)](View/disclosureGroupStyle.zh-Hans.md) modifier.

To create a custom disclosure group style, declare a type that conforms to `DisclosureGroupStyle`. Implement the [makeBody(configuration:)](DisclosureGroupStyle/makeBody_configuration.zh-Hans.md) method to return a view that composes the elements of the `configuration` that SwiftUI provides to your method.

```swift
struct MyDisclosureStyle: DisclosureGroupStyle {
    func makeBody(configuration: Configuration) -> some View {
        VStack {
            Button {
                withAnimation {
                    configuration.isExpanded.toggle()
                }
            } label: {
                HStack(alignment: .firstTextBaseline) {
                    configuration.label
                    Spacer()
                    Text(configuration.isExpanded ? "hide" : "show")
                        .foregroundColor(.accentColor)
                        .font(.caption.lowercaseSmallCaps())
                        .animation(nil, value: configuration.isExpanded)
                }
                .contentShape(Rectangle())
            }
            .buttonStyle(.plain)
            if configuration.isExpanded {
                configuration.content
            }
        }
    }
}
```

A type conforming to this protocol inherits `@preconcurrency @MainActor` isolation from the protocol if the conformance is included in the type’s base declaration:

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

Isolation to the main actor is the default, but it’s not required. Declare the conformance in an extension to opt out of main actor isolation:

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## Getting the styles

- **automatic**: A disclosure group style that resolves its appearance automatically based on the current context.

## Creating custom disclosure group styles

- **makeBody(configuration:)**: Creates a view that represents the body of a disclosure group.
- **DisclosureGroupStyleConfiguration**: The properties of a disclosure group instance.
- **DisclosureGroupStyle.Configuration**: The properties of a disclosure group instance.
- **Body**: A view that represents the body of a disclosure group.

## Supporting types

- **AutomaticDisclosureGroupStyle**: A disclosure group style that resolves its appearance automatically based on the current context.

## Styling collection views

- **listStyle(_:)**: Sets the style for lists within this view.
- **ListStyle**: A protocol that describes the behavior and appearance of a list.
- **tableStyle(_:)**: Sets the style for tables within this view.
- **TableStyle**: A type that applies a custom appearance to all tables within a view.
- **TableStyleConfiguration**: The properties of a table.
- **disclosureGroupStyle(_:)**: Sets the style for disclosure groups within this view.

## Conforming Types

- AutomaticDisclosureGroupStyle

