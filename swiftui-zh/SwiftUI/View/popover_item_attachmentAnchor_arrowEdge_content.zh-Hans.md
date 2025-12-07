--- 来源：https://developer.apple.com/documentation/SwiftUI/View/popover(item:attachmentAnchor:arrowEdge:content:)

抓取时间：2025-12-02T17:30:06Z

---

# popover(item:attachmentAnchor:arrowEdge:content:)

**实例方法**

使用给定的 item 作为弹出框内容的数据源来呈现弹出框。

## 声明

```swift
nonisolated func popover<Item, Content>(item: Binding<Item?>, attachmentAnchor: PopoverAttachmentAnchor = .rect(.bounds), arrowEdge: Edge? = nil, @ViewBuilder content: @escaping (Item) -> Content) -> some View where Item : Identifiable, Content : View

```

## 参数

- **item**：指向弹出框可选数据源的绑定。当 `item` 不为 `nil` 时，系统会将内容传递给修饰符的闭包。您可以使用此内容填充您创建的弹出框的字段，该弹出框将显示给用户。如果 `item` 发生更改，系统将关闭当前显示的弹出框，并使用相同的流程将其替换为新的弹出框。

- **attachmentAnchor**：定义弹出框连接点的定位锚点。默认值为 [bounds](../Anchor/Source/bounds.zh-Hans.md)。

- **arrowEdge**：定义弹出框箭头位置的 `attachmentAnchor` 的边缘。默认值为 `nil`，这意味着系统允许任何箭头边缘。

- **content**：返回弹出框内容的闭包。

## 讨论

当您需要显示包含来自自定义数据源的内容的弹出框时，请使用此方法。以下示例使用 `PopoverModel` 结构中的数据来填充 `content` 闭包中的视图，该视图会显示在弹出框中：

```swift
struct PopoverExample: View {
    @State private var popover: PopoverModel?

    var body: some View {
        Button("Show Popover") {
            popover = PopoverModel(message: "Custom Message")
        }
        .popover(item: $popover, arrowEdge: .bottom) { detail in
            Text("\(detail.message)")
                .padding()
        }
    }
}

struct PopoverModel: Identifiable {
    var id: String { message }
    let message: String
}
```

### 穿透效果

在 visionOS 中，大多数系统呈现默认带有穿透效果。要更改封闭呈现穿透遮挡内容的方式，请使用 [presentationBreakthroughEffect(_:)](presentationBreakthroughEffect.zh-Hans.md)，如下例所示：

```swift
.popover(item: $popover) { detail in
    Text("\(detail.message)")
        .padding()
        .presentationBreakthroughEffect(.prominent)
}
```

## 显示工作表、封面或弹出框

- **sheet(isPresented:onDismiss:content:)**：当您提供的布尔值绑定为真时，显示工作表。

- **sheet(item:onDismiss:content:)**：使用给定项作为工作表内容的数据源来显示工作表。

- **fullScreenCover(isPresented:onDismiss:content:)**：当绑定到您提供的布尔值且该值为真时，显示一个尽可能覆盖屏幕的模态视图。

- **fullScreenCover(item:onDismiss:content:)**：使用您提供的绑定作为工作表内容的数据源，显示一个尽可能覆盖屏幕的模态视图。

- **popover(isPresented:attachmentAnchor:arrowEdge:content:)**：当给定条件为真时，显示一个弹出框。

- **PopoverAttachmentAnchor**：弹出框的附件锚点。


---
source: https://developer.apple.com/documentation/SwiftUI/View/popover(item:attachmentAnchor:arrowEdge:content:)
crawled: 2025-12-02T17:30:06Z
---

# popover(item:attachmentAnchor:arrowEdge:content:)

**Instance Method**

Presents a popover using the given item as a data source for the popover’s content.

## Declaration

```swift
nonisolated func popover<Item, Content>(item: Binding<Item?>, attachmentAnchor: PopoverAttachmentAnchor = .rect(.bounds), arrowEdge: Edge? = nil, @ViewBuilder content: @escaping (Item) -> Content) -> some View where Item : Identifiable, Content : View

```

## Parameters

- **item**: A binding to an optional source of truth for the popover. When `item` is non-`nil`, the system passes the contents to the modifier’s closure. You use this content to populate the fields of a popover that you create that the system displays to the user. If `item` changes, the system dismisses the currently presented popover and replaces it with a new popover using the same process.
- **attachmentAnchor**: The positioning anchor that defines the attachment point of the popover. The default is [bounds](../Anchor/Source/bounds.zh-Hans.md).
- **arrowEdge**: The edge of the `attachmentAnchor` that defines the location of the popover’s arrow. The default is `nil`, which results in the system allowing any arrow edge.
- **content**: A closure returning the content of the popover.

## Discussion

Use this method when you need to present a popover with content from a custom data source. The example below uses data in the `PopoverModel` structure to populate the view in the `content` closure that the popover displays to the user:

```swift
struct PopoverExample: View {
    @State private var popover: PopoverModel?

    var body: some View {
        Button("Show Popover") {
            popover = PopoverModel(message: "Custom Message")
        }
        .popover(item: $popover, arrowEdge: .bottom) { detail in
            Text("\(detail.message)")
                .padding()
        }
    }
}

struct PopoverModel: Identifiable {
    var id: String { message }
    let message: String
}
```





### Breakthrough effect

In visionOS, most system presentations appear with a breakthrough effect by default. To change how the enclosing presentation breaks through content occluding it, use [presentationBreakthroughEffect(_:)](presentationBreakthroughEffect.zh-Hans.md), like in the following example:

```swift
.popover(item: $popover) { detail in
    Text("\(detail.message)")
        .padding()
        .presentationBreakthroughEffect(.prominent)
}
```

## Showing a sheet, cover, or popover

- **sheet(isPresented:onDismiss:content:)**: Presents a sheet when a binding to a Boolean value that you provide is true.
- **sheet(item:onDismiss:content:)**: Presents a sheet using the given item as a data source for the sheet’s content.
- **fullScreenCover(isPresented:onDismiss:content:)**: Presents a modal view that covers as much of the screen as possible when binding to a Boolean value you provide is true.
- **fullScreenCover(item:onDismiss:content:)**: Presents a modal view that covers as much of the screen as possible using the binding you provide as a data source for the sheet’s content.
- **popover(isPresented:attachmentAnchor:arrowEdge:content:)**: Presents a popover when a given condition is true.
- **PopoverAttachmentAnchor**: An attachment anchor for a popover.

