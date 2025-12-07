--- 来源：https://developer.apple.com/documentation/SwiftUI/View/popoverTip(_:isPresented:attachmentAnchor:arrowEdges:action:)

抓取时间：2025-12-02T17:25:06Z

---

# popoverTip(_:isPresented:attachmentAnchor:arrowEdges:action:)

**实例方法**

在修改后的视图上显示弹出提示。

## 声明

```swift
@preconcurrency nonisolated func popoverTip(_ tip: (any Tip)?, isPresented: Binding<Bool>? = nil, attachmentAnchor: PopoverAttachmentAnchor = .rect(.bounds), arrowEdges: Edge.Set, action: @escaping @MainActor (Tips.Action) -> Void = { _ in }) -> some View

```

## 参数

- **tip**：要显示的提示。

- **isPresented**：一个绑定，当显示提示时会自动更新为 true。可以更改此值来临时隐藏或显示当前可显示的提示。如果此值为 `nil`，则弹出框将根据提示的状态和显示规则自动关闭。如果此值为 `nil`，则弹出框将根据提示的状态和显示规则自动关闭。

- **attachmentAnchor**：定义弹出框连接点的定位锚点。默认值为 bounds。

- **arrowEdges**：允许弹出框箭头定位的边缘。

- **action**：用户触发提示操作时要执行的闭包。

### 讨论

当提示符合显示条件时，使用此修饰符可在现有视图上以弹出框的形式显示提示。

```swift
struct TrailRow: View {
    let trail: Trail

    var body: some View {
        VStack {
            HStack {
                Text(trail.name)

                Button(action: trail.favorite) {
                    Image(systemName: "star")
                }
            }
        }
        .popoverTip(FavoriteTrailTip(), attachmentAnchor: .point(.center), arrowEdges: .vertical)
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/popoverTip(_:isPresented:attachmentAnchor:arrowEdges:action:)
crawled: 2025-12-02T17:25:06Z
---

# popoverTip(_:isPresented:attachmentAnchor:arrowEdges:action:)

**Instance Method**

Presents a popover tip on the modified view.

## Declaration

```swift
@preconcurrency nonisolated func popoverTip(_ tip: (any Tip)?, isPresented: Binding<Bool>? = nil, attachmentAnchor: PopoverAttachmentAnchor = .rect(.bounds), arrowEdges: Edge.Set, action: @escaping @MainActor (Tips.Action) -> Void = { _ in }) -> some View

```

## Parameters

- **tip**: The tip to display.
- **isPresented**: A binding that will automatically update to true when a tip is displayed. This value can be changed to temporarily hide or show a currently displayable tip. If this value is `nil`, the popover will automatically be dismissed based on the tip’s status and display rules. If this value is `nil`, the popover will automatically be dismissed based on the tip’s status and display rules.
- **attachmentAnchor**: The positioning anchor that defines the attachment point of the popover. The default is bounds.
- **arrowEdges**: The edges that the popover’s arrow is allowed to be positioned.
- **action**: The closure to perform when the user triggers a tip’s action.

### Discussion

Use this modifier to present a tip as a popover on an existing view when the tip becomes eligible for display.

```swift
struct TrailRow: View {
    let trail: Trail

    var body: some View {
        VStack {
            HStack {
                Text(trail.name)

                Button(action: trail.favorite) {
                    Image(systemName: "star")
                }
            }
        }
        .popoverTip(FavoriteTrailTip(), attachmentAnchor: .point(.center), arrowEdges: .vertical)
    }
}
```

