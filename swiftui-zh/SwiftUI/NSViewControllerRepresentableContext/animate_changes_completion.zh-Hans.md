--- 来源：https://developer.apple.com/documentation/SwiftUI/NSViewControllerRepresentableContext/animate(changes:completion:)

抓取时间：2025-12-03T06:58:00Z

---

# animate(changes:completion:)

**实例方法**

使用当前事务中的动画来为更改添加动画效果。

## 声明

```swift
@backDeployed(before: macOS 15.4)
@MainActor @preconcurrency func animate(changes: () -> Void, completion: (() -> Void)? = nil)
```

## 参数

- **changes**：用于更改可动画属性的闭包。

- **completion**：动画完成后要执行的闭包。

## 说明

此方法结合了 doc://com.apple.documentation/documentation/appkit/nsanimationcontext/4433144-animate 和当前事务的动画。当您使用 [withAnimation(_:_:)](../withAnimation.zh-Hans.md) 启动 SwiftUI 动画，并且 SwiftUI 状态发生改变导致可表示对象更新时，请使用此方法以相同的 `Animation` 时序来动画化可表示对象的更改。

```swift
struct ContentView: View {
    @State private var isCollapsed = false
    var body: some View {
        ZStack {
            MyDetailView(isCollapsed: isCollapsed)
            MyRepresentable(isCollapsed: $isCollapsed)
            Button("Collapse Content") {
                withAnimation(.bouncy) {
                    isCollapsed = true
                }
            }
        }
    }
}

struct MyRepresentable: NSViewControllerRepresentable {
    @Binding var isCollapsed: Bool

    func updateNSViewController(_ nsViewController: NSViewControllerType, context: Context) {
        if isCollapsed && !nsViewController.view.isCollapsed {
            context.animate {
                nsViewController.view.collapseSubview()
                nsViewController.view.layoutSubtreeIfNeeded()
            }
        }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/NSViewControllerRepresentableContext/animate(changes:completion:)
crawled: 2025-12-03T06:58:00Z
---

# animate(changes:completion:)

**Instance Method**

Animates changes using the animation in the current transaction.

## Declaration

```swift
@backDeployed(before: macOS 15.4)
@MainActor @preconcurrency func animate(changes: () -> Void, completion: (() -> Void)? = nil)
```

## Parameters

- **changes**: A closure that changes animatable properties.
- **completion**: A closure to execute after the animation completes.

## Discussion

This combines doc://com.apple.documentation/documentation/appkit/nsanimationcontext/4433144-animate with the current transaction’s animation. When you start a SwiftUI animation using [withAnimation(_:_:)](../withAnimation.zh-Hans.md) and have a mutated SwiftUI state that causes the representable object to update, use this method to animate changes in the representable object using the same `Animation` timing.

```swift
struct ContentView: View {
    @State private var isCollapsed = false
    var body: some View {
        ZStack {
            MyDetailView(isCollapsed: isCollapsed)
            MyRepresentable(isCollapsed: $isCollapsed)
            Button("Collapse Content") {
                withAnimation(.bouncy) {
                    isCollapsed = true
                }
            }
        }
    }
}

struct MyRepresentable: NSViewControllerRepresentable {
    @Binding var isCollapsed: Bool

    func updateNSViewController(_ nsViewController: NSViewControllerType, context: Context) {
        if isCollapsed && !nsViewController.view.isCollapsed {
            context.animate {
                nsViewController.view.collapseSubview()
                nsViewController.view.layoutSubtreeIfNeeded()
            }
        }
    }
}
```

