---
来源：https://developer.apple.com/documentation/SwiftUI/NSViewRepresentableContext/animate(变更：完成：)
抓取时间：2025-12-03T06:57:57Z
---

# animate(changes:completion:)

**实例方法**

使用当前事务中的动画演示更改。

## 声明

```swift
@backDeployed(before: macOS 15.4)
@MainActor @preconcurrency func animate(changes: () -> Void, completion: (() -> Void)? = nil)
```

## 参数

- **changes**：用于更改动画属性的闭包。
- **completion**：在动画完成后执行的闭包。

## 讨论

这将 doc://com.apple.documentation/documentation/appkit/nsanimationcontext/4433144-animate 与当前事务的动画相结合。当您使用 [withAnimation(_:_:)](../withAnimation.zh-Hans.md) 启动 SwiftUI 动画，并有一个导致可表示对象更新的突变 SwiftUI 状态时，使用此方法可以使用相同的 `Animation` 时序将可表示对象中的变化制作成动画。

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

struct MyRepresentable: NSViewRepresentable {
    @Binding var isCollapsed: Bool

    func updateNSView(_ nsView: NSViewType, context: Context) {
        if isCollapsed && !nsView.isCollapsed {
            context.animate {
                nsView.collapseSubview()
                nsView.layoutSubtreeIfNeeded()
            }
        }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/NSViewRepresentableContext/animate(changes:completion:)
crawled: 2025-12-03T06:57:57Z
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

struct MyRepresentable: NSViewRepresentable {
    @Binding var isCollapsed: Bool

    func updateNSView(_ nsView: NSViewType, context: Context) {
        if isCollapsed && !nsView.isCollapsed {
            context.animate {
                nsView.collapseSubview()
                nsView.layoutSubtreeIfNeeded()
            }
        }
    }
}
```

