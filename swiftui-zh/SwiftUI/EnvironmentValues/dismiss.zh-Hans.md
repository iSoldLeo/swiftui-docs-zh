---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/dismiss
抓取时间： 2025-12-02T17:21:09Z
---

# 解雇

**实例属性**

解除当前演示的操作。

## 声明

```swift
var dismiss: DismissAction { get }
```

## 讨论

使用此环境值获取当前[DismissAction](../DismissAction.zh-Hans.md) 的[Environment](../Environment.zh-Hans.md) 实例。然后调用该实例来执行解散操作。我们直接调用实例是因为它定义了一个 [callAsFunction()](../DismissAction/callAsFunction.zh-Hans.md) 方法，当我们调用实例时，Swift 会调用该方法。

您可以使用此操作来

- 解除模式化演示（如工作表或弹出式窗口）。
- 弹出当前视图。

在针对 iOS 18 和对齐版本的应用程序中，你还可以使用解散操作弹出折叠[NavigationSplitView](../NavigationSplitView.zh-Hans.md) 的隐式堆栈，或清除展开的拆分视图中的等效状态。

操作的具体行为取决于调用它的位置。例如，您可以创建一个按钮，在作为工作表的视图中调用[DismissAction](../DismissAction.zh-Hans.md)：

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

当您显示`SheetContents` 视图时，别人可以通过点击或单击工作表按钮来取消工作表：

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

确保在适当的环境中定义操作。例如，不要重组上例中的`DetailView`，使其创建`dismiss` 属性，并从[sheet(item:onDismiss:content:)](../View/sheet_item_onDismiss_content.zh-Hans.md) 视图修改器的`content` 闭包中调用该属性：

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

如果您这样做，工作表就会无法取消，因为该操作适用于您声明它的环境，即详细视图的环境，而不是工作表的环境。事实上，在 macOS 和 iPadOS 中，如果`DetailView` 是窗口的根视图，则解散操作会关闭窗口。

驳回操作对当前未显示的视图不起作用。如果需要查询 SwiftUI 当前是否正在显示某个视图，请读取 [isPresented](isPresented.zh-Hans.md) 环境值。



## 取消显示

- **isPresented**：布尔值，表示与此环境相关的视图当前是否正在显示。
- **DismissAction**：用于取消演示的操作。
- **interactiveDismissDisabled(_:)**：有条件地防止弹出窗口、工作表和检查器等演示文稿的交互式解散。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/dismiss
crawled: 2025-12-02T17:21:09Z
---

# dismiss

**Instance Property**

An action that dismisses the current presentation.

## Declaration

```swift
var dismiss: DismissAction { get }
```

## Discussion

Use this environment value to get the [DismissAction](../DismissAction.zh-Hans.md) instance for the current [Environment](../Environment.zh-Hans.md). Then call the instance to perform the dismissal. You call the instance directly because it defines a [callAsFunction()](../DismissAction/callAsFunction.zh-Hans.md) method that Swift calls when you call the instance.

You can use this action to:

- Dismiss a modal presentation, like a sheet or a popover.
- Pop the current view from a [NavigationStack](../NavigationStack.zh-Hans.md).

On apps targetting iOS 18 and aligned releases, you also use the dismiss action to pop the implicit stack of a collapsed [NavigationSplitView](../NavigationSplitView.zh-Hans.md), or clear the equivalent state in an expanded split view.

The specific behavior of the action depends on where you call it from. For example, you can create a button that calls the [DismissAction](../DismissAction.zh-Hans.md) inside a view that acts as a sheet:

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

Be sure that you define the action in the appropriate environment. For example, don’t reorganize the `DetailView` in the example above so that it creates the `dismiss` property and calls it from the [sheet(item:onDismiss:content:)](../View/sheet_item_onDismiss_content.zh-Hans.md) view modifier’s `content` closure:

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

The dismiss action has no effect on a view that isn’t currently presented. If you need to query whether SwiftUI is currently presenting a view, read the [isPresented](isPresented.zh-Hans.md) environment value.



## Dismissing a presentation

- **isPresented**: A Boolean value that indicates whether the view associated with this environment is currently presented.
- **DismissAction**: An action that dismisses a presentation.
- **interactiveDismissDisabled(_:)**: Conditionally prevents interactive dismissal of presentations like popovers, sheets, and inspectors.

