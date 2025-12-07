---
来源：https://developer.apple.com/documentation/SwiftUI/TabContent/popover(isPresented:attachmentAnchor:arrowEdge:content:)
抓取时间：2025-12-01T10:50:50Z
---

# popover(isPresented:attachmentAnchor:arrowEdge:content:)

**实例方法**

当给定条件为真时显示弹出窗口。

## 声明

```swift
nonisolated func popover<Content>(isPresented: Binding<Bool>, attachmentAnchor: PopoverAttachmentAnchor = .rect(.bounds), arrowEdge: Edge? = nil, @ViewBuilder content: @escaping () -> Content) -> some TabContent<Self.TabValue> where Content : View

```

## 参数

- **isPresented**：与布尔值的绑定，用于决定是否显示从修改器的 `content` 闭包返回的弹出窗口内容。
- **attachmentAnchor**：定位锚点，用于定义弹出窗口的连接点。默认为[bounds](../Anchor/Source/bounds.zh-Hans.md)。
- **arrowEdge**：在 macOS 中定义弹出窗口箭头位置的`attachmentAnchor` 边沿。默认值为[top](../Edge/top.zh-Hans.md)。
- **content**：返回弹出窗口内容的闭包。

## 讨论

使用本方法可以显示一个弹出窗口，其内容是当绑定的布尔变量为`true`时提供的 SwiftUI 视图。在下面的示例中，每当用户按下 "Show Popover（显示弹出窗口）"按钮切换`isShowingPopover` 状态变量时，弹出窗口就会显示：

```swift
struct PopoverExample: View {
    @State private var isShowingPopover = false

    var body: some View {
        TabView {
            Tab("Popover Anchor", systemImage: "arrow.down") {
                Button("Show Popover") {
                    self.isShowingPopover = true
                }
            }
            .popover(isPresented: $isShowingPopover) {
                Text("Popover Content")
                    .padding()
            }
        }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/TabContent/popover(isPresented:attachmentAnchor:arrowEdge:content:)
crawled: 2025-12-01T10:50:50Z
---

# popover(isPresented:attachmentAnchor:arrowEdge:content:)

**Instance Method**

Presents a popover when a given condition is true.

## Declaration

```swift
nonisolated func popover<Content>(isPresented: Binding<Bool>, attachmentAnchor: PopoverAttachmentAnchor = .rect(.bounds), arrowEdge: Edge? = nil, @ViewBuilder content: @escaping () -> Content) -> some TabContent<Self.TabValue> where Content : View

```

## Parameters

- **isPresented**: A binding to a Boolean value that determines whether to present the popover content that you return from the modifier’s `content` closure.
- **attachmentAnchor**: The positioning anchor that defines the attachment point of the popover. The default is [bounds](../Anchor/Source/bounds.zh-Hans.md).
- **arrowEdge**: The edge of the `attachmentAnchor` that defines the location of the popover’s arrow in macOS. The default is [top](../Edge/top.zh-Hans.md).
- **content**: A closure returning the content of the popover.

## Discussion

Use this method to show a popover whose contents are a SwiftUI view that you provide when a bound Boolean variable is `true`. In the example below, a popover displays whenever the user toggles the `isShowingPopover` state variable by pressing the “Show Popover” button:

```swift
struct PopoverExample: View {
    @State private var isShowingPopover = false

    var body: some View {
        TabView {
            Tab("Popover Anchor", systemImage: "arrow.down") {
                Button("Show Popover") {
                    self.isShowingPopover = true
                }
            }
            .popover(isPresented: $isShowingPopover) {
                Text("Popover Content")
                    .padding()
            }
        }
    }
}
```

