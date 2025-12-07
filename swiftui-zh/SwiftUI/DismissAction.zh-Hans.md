--- 来源：https://developer.apple.com/documentation/SwiftUI/DismissAction
抓取时间：2025-12-02T17:21:09Z

---

# DismissAction

**Structure**

一个用于关闭演示的操作。

## 声明

```swift
@MainActor @preconcurrency struct DismissAction
```

## 概述

使用 [dismiss](EnvironmentValues/dismiss.zh-Hans.md) 环境变量值获取给定 [Environment](Environment.zh-Hans.md) 对应的此结构实例。然后调用该实例来执行关闭操作。之所以直接调用实例，是因为它定义了一个 [callAsFunction()](DismissAction/callAsFunction.zh-Hans.md) 方法，Swift 会在调用该实例时调用此方法。

您可以使用此操作来：

- 关闭模态演示，例如工作表或弹出框。

- 从 [NavigationStack](NavigationStack.zh-Hans.md) 中弹出当前视图。

在面向 iOS 18 及后续版本的应用中，您还可以使用 dismiss 操作弹出已折叠的 [NavigationSplitView](NavigationSplitView.zh-Hans.md) 的隐式堆栈，或清除已展开的拆分视图中的相应状态。

此操作的具体行为取决于调用位置。例如，您可以创建一个按钮，该按钮调用作为工作表的视图中的 [DismissAction](DismissAction.zh-Hans.md)：

```swift
private struct SheetContents: View {
    @Environment(\.dismiss) private var dismiss

    var body: some View {
        Button("Done") {
            dismiss()
        }
    }
}
```

当您显示 `SheetContents` 视图时，用户可以通过点击工作表按钮来关闭工作表：

```swift
private struct DetailView: View {
    @State private var isSheetPresented = false

    var body: some View {
        Button("Show Sheet") {
            isSheetPresented = true
        }
        .sheet(isPresented: $isSheetPresented) {
            SheetContents()
        }
    }
}
```

请确保在适当的环境中定义此操作。例如，不要像上面示例中那样重新组织 `DetailView`，使其创建 `dismiss` 属性并从 [sheet(item:onDismiss:content:)](View/sheet_item_onDismiss_content.zh-Hans.md) 视图修饰符的 `content` 闭包中调用它：

```swift
private struct DetailView: View {
    @State private var isSheetPresented = false
    @Environment(\.dismiss) private var dismiss // Applies to DetailView.

    var body: some View {
        Button("Show Sheet") {
            isSheetPresented = true
        }
        .sheet(isPresented: $isSheetPresented) {
            Button("Done") {
                dismiss() // Fails to dismiss the sheet.
            }
        }
    }
}
```

如果这样做，则工作表将无法关闭，因为该操作应用于您声明它的环境（即详情视图的环境），而不是工作表的环境。实际上，在 macOS 和 iPadOS 中，如果 `DetailView` 是窗口的根视图，则关闭操作会关闭窗口。

关闭操作对当前未显示的视图无效。如果您需要查询 SwiftUI 当前是否显示某个视图，请读取 [isPresented](EnvironmentValues/isPresented.zh-Hans.md) 环境值。

## 调用操作

- **callAsFunction()**：如果视图当前处于显示状态，则将其关闭。

## 关闭显示

- **isPresented**：一个布尔值，指示与此环境关联的视图当前是否处于显示状态。

- **dismiss**：关闭当前显示的操作。

- **interactiveDismissDisabled(_:)**：有条件地阻止交互式关闭显示，例如弹出框、工作表和检查器。

## 符合以下规范

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/DismissAction
crawled: 2025-12-02T17:21:09Z
---

# DismissAction

**Structure**

An action that dismisses a presentation.

## Declaration

```swift
@MainActor @preconcurrency struct DismissAction
```

## Overview

Use the [dismiss](EnvironmentValues/dismiss.zh-Hans.md) environment value to get the instance of this structure for a given [Environment](Environment.zh-Hans.md). Then call the instance to perform the dismissal. You call the instance directly because it defines a [callAsFunction()](DismissAction/callAsFunction.zh-Hans.md) method that Swift calls when you call the instance.

You can use this action to:

- Dismiss a modal presentation, like a sheet or a popover.
- Pop the current view from a [NavigationStack](NavigationStack.zh-Hans.md).

On apps targeting iOS 18 and aligned releases, you also use the dismiss action to pop the implicit stack of a collapsed [NavigationSplitView](NavigationSplitView.zh-Hans.md), or clear the equivalent state in an expanded split view.

The specific behavior of the action depends on where you call it from. For example, you can create a button that calls the [DismissAction](DismissAction.zh-Hans.md) inside a view that acts as a sheet:

```swift
private struct SheetContents: View {
    @Environment(\.dismiss) private var dismiss

    var body: some View {
        Button("Done") {
            dismiss()
        }
    }
}
```

When you present the `SheetContents` view, someone can dismiss the sheet by tapping or clicking the sheet’s button:

```swift
private struct DetailView: View {
    @State private var isSheetPresented = false

    var body: some View {
        Button("Show Sheet") {
            isSheetPresented = true
        }
        .sheet(isPresented: $isSheetPresented) {
            SheetContents()
        }
    }
}
```

Be sure that you define the action in the appropriate environment. For example, don’t reorganize the `DetailView` in the example above so that it creates the `dismiss` property and calls it from the [sheet(item:onDismiss:content:)](View/sheet_item_onDismiss_content.zh-Hans.md) view modifier’s `content` closure:

```swift
private struct DetailView: View {
    @State private var isSheetPresented = false
    @Environment(\.dismiss) private var dismiss // Applies to DetailView.

    var body: some View {
        Button("Show Sheet") {
            isSheetPresented = true
        }
        .sheet(isPresented: $isSheetPresented) {
            Button("Done") {
                dismiss() // Fails to dismiss the sheet.
            }
        }
    }
}
```

If you do this, the sheet fails to dismiss because the action applies to the environment where you declared it, which is that of the detail view, rather than the sheet. In fact, in macOS and iPadOS, if the `DetailView` is the root view of a window, the dismiss action closes the window instead.

The dismiss action has no effect on a view that isn’t currently presented. If you need to query whether SwiftUI is currently presenting a view, read the [isPresented](EnvironmentValues/isPresented.zh-Hans.md) environment value.



## Calling the action

- **callAsFunction()**: Dismisses the view if it is currently presented.

## Dismissing a presentation

- **isPresented**: A Boolean value that indicates whether the view associated with this environment is currently presented.
- **dismiss**: An action that dismisses the current presentation.
- **interactiveDismissDisabled(_:)**: Conditionally prevents interactive dismissal of presentations like popovers, sheets, and inspectors.

## Conforms To

- Sendable
- SendableMetatype

