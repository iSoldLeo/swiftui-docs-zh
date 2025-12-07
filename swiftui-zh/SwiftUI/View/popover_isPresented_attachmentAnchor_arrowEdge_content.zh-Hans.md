--- 来源：https://developer.apple.com/documentation/SwiftUI/View/popover(isPresented:attachmentAnchor:arrowEdge:content:)

抓取时间：2025-12-02T17:30:07Z

---

# popover(isPresented:attachmentAnchor:arrowEdge:content:)

**实例方法**

当给定条件为真时，显示弹出框。

## 声明

```swift
nonisolated func popover<Content>(isPresented: Binding<Bool>, attachmentAnchor: PopoverAttachmentAnchor = .rect(.bounds), arrowEdge: Edge? = nil, @ViewBuilder content: @escaping () -> Content) -> some View where Content : View

```

## 参数

- **isPresented**：绑定到一个布尔值，该值决定是否显示从修饰符的闭包返回的弹出框内容。`content`

- **attachmentAnchor**：定义弹出框连接点的定位锚点。默认值为 [bounds](../Anchor/Source/bounds.zh-Hans.md)。

- **arrowEdge**：定义弹出框箭头位置的 `attachmentAnchor` 的边缘。默认值为 `nil`，这意味着系统允许任何箭头边缘。

- **content**：返回弹出框内容的闭包。

## 讨论

当绑定的布尔变量为 `true` 时，使用此方法显示一个弹出框，其内容为您提供的 SwiftUI 视图。在下面的示例中，当用户按下“显示弹出框”按钮切换 `isShowingPopover` 状态变量时，将显示一个弹出框：

```swift
struct PopoverExample: View {
    @State private var isShowingPopover = false

    var body: some View {
        Button("Show Popover") {
            self.isShowingPopover = true
        }
        .popover(
            isPresented: $isShowingPopover, arrowEdge: .bottom
        ) {
            Text("Popover Content")
                .padding()
        }
    }
}
```

### 突破效果

在 visionOS 中，大多数系统演示默认带有突破效果。要更改外层视图穿透遮挡内容的方式，请使用 [presentationBreakthroughEffect(_:)](presentationBreakthroughEffect.zh-Hans.md)，如下例所示：

```swift
.popover(isPresented: $isShowingPopover) {
    Text("Popover Content")
        .padding()
        .presentationBreakthroughEffect(.prominent)
}
```

## 显示工作表、封面或弹出框

- **sheet(isPresented:onDismiss:content:)**：当绑定到您提供的布尔值且该值为真时，显示一个工作表。

- **sheet(item:onDismiss:content:)**：使用给定项作为工作表内容的数据源来显示工作表。

- **fullScreenCover(isPresented:onDismiss:content:)**：当绑定到您提供的布尔值且该值为真时，显示一个尽可能覆盖屏幕的模态视图。

- **fullScreenCover(item:onDismiss:content:)**：使用您提供的绑定作为工作表内容的数据源，显示一个尽可能覆盖屏幕的模态视图。

- **popover(item:attachmentAnchor:arrowEdge:content:)**：使用指定项目作为弹出框内容的数据源，显示一个弹出框。

- **PopoverAttachmentAnchor**：弹出框的附件锚点。


---
source: https://developer.apple.com/documentation/SwiftUI/View/popover(isPresented:attachmentAnchor:arrowEdge:content:)
crawled: 2025-12-02T17:30:07Z
---

# popover(isPresented:attachmentAnchor:arrowEdge:content:)

**Instance Method**

Presents a popover when a given condition is true.

## Declaration

```swift
nonisolated func popover<Content>(isPresented: Binding<Bool>, attachmentAnchor: PopoverAttachmentAnchor = .rect(.bounds), arrowEdge: Edge? = nil, @ViewBuilder content: @escaping () -> Content) -> some View where Content : View

```

## Parameters

- **isPresented**: A binding to a Boolean value that determines whether to present the popover content that you return from the modifier’s `content` closure.
- **attachmentAnchor**: The positioning anchor that defines the attachment point of the popover. The default is [bounds](../Anchor/Source/bounds.zh-Hans.md).
- **arrowEdge**: The edge of the `attachmentAnchor` that defines the location of the popover’s arrow. The default is `nil`, which results in the system allowing any arrow edge.
- **content**: A closure returning the content of the popover.

## Discussion

Use this method to show a popover whose contents are a SwiftUI view that you provide when a bound Boolean variable is `true`. In the example below, a popover displays whenever the user toggles the `isShowingPopover` state variable by pressing the “Show Popover” button:

```swift
struct PopoverExample: View {
    @State private var isShowingPopover = false

    var body: some View {
        Button("Show Popover") {
            self.isShowingPopover = true
        }
        .popover(
            isPresented: $isShowingPopover, arrowEdge: .bottom
        ) {
            Text("Popover Content")
                .padding()
        }
    }
}
```





### Breakthrough effect

In visionOS, most system presentations appear with a breakthrough effect by default. To change how the enclosing presentation breaks through content occluding it, use [presentationBreakthroughEffect(_:)](presentationBreakthroughEffect.zh-Hans.md), like in the following example:

```swift
.popover(isPresented: $isShowingPopover) {
    Text("Popover Content")
        .padding()
        .presentationBreakthroughEffect(.prominent)
}
```

## Showing a sheet, cover, or popover

- **sheet(isPresented:onDismiss:content:)**: Presents a sheet when a binding to a Boolean value that you provide is true.
- **sheet(item:onDismiss:content:)**: Presents a sheet using the given item as a data source for the sheet’s content.
- **fullScreenCover(isPresented:onDismiss:content:)**: Presents a modal view that covers as much of the screen as possible when binding to a Boolean value you provide is true.
- **fullScreenCover(item:onDismiss:content:)**: Presents a modal view that covers as much of the screen as possible using the binding you provide as a data source for the sheet’s content.
- **popover(item:attachmentAnchor:arrowEdge:content:)**: Presents a popover using the given item as a data source for the popover’s content.
- **PopoverAttachmentAnchor**: An attachment anchor for a popover.

