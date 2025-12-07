--- 来源：https://developer.apple.com/documentation/swiftui/findcontext

抓取时间：2025-12-04T13:10:44Z

---

# FindContext

**Structure**

支持文本编辑的视图的查找导航器状态。

## 声明

```swift
struct FindContext
```

## 概述

支持文本编辑的视图可以使用此信息来实现查找导航器，该导航器可通过与 SwiftUI 其他部分相同的修饰符进行控制。

例如，以下示例展示了一个由查找上下文驱动的最小查找导航器实现，如果未提供 `isPresented` 绑定，则会回退到本地状态：

```swift
struct FindNavigatorDrivenTextInput: View {
    @State var text: String = ""
    @State var showFindNavigator = false
    @Environment(\.findContext) var findContext
    var body: some View {
        MyTextInputView(text: $text)
            .overlay(alignment: .topTrailing) {
                if let context = findContext &&
                    context.isPresented?.wrappedValue ?? showFindNavigator
                {
                    HStack {
                        FindInputView(text: text)
                        if context.allowedOperations == .findAndReplace {
                            ReplaceInputView(text: $text)
                        }
                        Button("Close") {
                            context.isPresented?.wrappedValue = false
                            showFindNavigator = false
                        }
                    }
                } else {
                    Button("Show Find Navigator") {
                        context.isPresented?.wrappedValue = true
                        showFindNavigator = true
                    }
                }
            }
    }
}
```

## 实例属性

- **isPresented**：控制是否显示查找导航器的绑定，如果未通过 [findNavigator(isPresented:)](View/findNavigator_isPresented.zh-Hans.md) 修饰符提供绑定，则为 nil。

- **supportsReplace**：此上下文中的查找导航器是否应支持替换。

## 在视图中搜索文本

- **findNavigator(isPresented:)**：以编程方式显示文本编辑器视图的查找和替换界面。

- **findDisabled(_:)**：阻止在文本编辑器中执行查找和替换操作。

- **replaceDisabled(_:)**：阻止在文本编辑器中进行替换操作。

## 符合以下规范

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/swiftui/findcontext
crawled: 2025-12-04T13:10:44Z
---

# FindContext

**Structure**

The status of the find navigator for views which support text editing.

## Declaration

```swift
struct FindContext
```

## Overview

Views which support text editing can use this information to implement a a find navigator that is controlled using the modifiers used for controlling the find navigator throughout the rest of SwiftUI.

For example, the following shows a minimal find navigator implementation driven by the find context which falls back to local state if no `isPresented` binding is provided:

```swift
struct FindNavigatorDrivenTextInput: View {
    @State var text: String = ""
    @State var showFindNavigator = false
    @Environment(\.findContext) var findContext
    var body: some View {
        MyTextInputView(text: $text)
            .overlay(alignment: .topTrailing) {
                if let context = findContext &&
                    context.isPresented?.wrappedValue ?? showFindNavigator
                {
                    HStack {
                        FindInputView(text: text)
                        if context.allowedOperations == .findAndReplace {
                            ReplaceInputView(text: $text)
                        }
                        Button("Close") {
                            context.isPresented?.wrappedValue = false
                            showFindNavigator = false
                        }
                    }
                } else {
                    Button("Show Find Navigator") {
                        context.isPresented?.wrappedValue = true
                        showFindNavigator = true
                    }
                }
            }
    }
}
```

## Instance Properties

- **isPresented**: A binding controlling if the find navigator is presented, or nil if no binding has been provided via the [findNavigator(isPresented:)](View/findNavigator_isPresented.zh-Hans.md) modifier.
- **supportsReplace**: If the find navigators in this context should support replacing.

## Searching for text in a view

- **findNavigator(isPresented:)**: Programmatically presents the find and replace interface for text editor views.
- **findDisabled(_:)**: Prevents find and replace operations in a text editor.
- **replaceDisabled(_:)**: Prevents replace operations in a text editor.

## Conforms To

- Sendable
- SendableMetatype

