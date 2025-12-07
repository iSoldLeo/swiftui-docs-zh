---
来源： https://developer.apple.com/documentation/SwiftUI/Transaction/dismissBehavior
抓取时间： 2025-12-03T06:17:22Z
---

# dismissBehavior

**实例属性**



## 声明

```swift
var dismissBehavior: DismissBehavior { get set }
```

## 讨论

默认值为 `.interactive`。

通过使用`.destructive` 值，您可以使用此属性来取消可能正在显示模式演示的窗口：

```swift
struct DismissWindowButton: View {
    @Environment(\.dismissWindow) private var dismissWindow

    var body: some View {
        Button("Close Auxiliary Window") {
            withTransaction(\.dismissBehavior, .destructive) {
                dismissWindow(id: "auxiliary")
            }
        }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/Transaction/dismissBehavior
crawled: 2025-12-03T06:17:22Z
---

# dismissBehavior

**Instance Property**

The behavior for how windows will dismiss programmatically when used in conjunction with [DismissWindowAction](../DismissWindowAction.zh-Hans.md).

## Declaration

```swift
var dismissBehavior: DismissBehavior { get set }
```

## Discussion

The default value is `.interactive`.

You can use this property to dismiss windows which may be showing a modal presentation by using the `.destructive` value:

```swift
struct DismissWindowButton: View {
    @Environment(\.dismissWindow) private var dismissWindow

    var body: some View {
        Button("Close Auxiliary Window") {
            withTransaction(\.dismissBehavior, .destructive) {
                dismissWindow(id: "auxiliary")
            }
        }
    }
}
```

