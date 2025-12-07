---
来源：https://developer.apple.com/documentation/SwiftUI/TabContent/popover(item:attachmentAnchor:arrowEdge:content:)
抓取时间： 2025-12-01T10:50:51Z


# popover(item:attachmentAnchor:arrowEdge:content:)

**实例方法**

使用给定项目作为弹出窗口内容的数据源，显示弹出窗口。

## 声明

```swift
nonisolated func popover<Item, Content>(item: Binding<Item?>, attachmentAnchor: PopoverAttachmentAnchor = .rect(.bounds), arrowEdge: Edge? = nil, @ViewBuilder content: @escaping (Item) -> Content) -> some TabContent<Self.TabValue> where Item : Identifiable, Content : View

```

## 参数

- **item**：与弹出窗口的可选真相来源绑定。当`item` 非`nil` 时，系统会将内容传递给修饰符的闭包。您可以使用这些内容来填充您创建的弹出窗口中的字段，系统会将弹出窗口显示给用户。如果`item` 发生变化，系统将取消当前显示的弹出窗口，并使用相同的流程用新的弹出窗口替换它。
- **attachmentAnchor**：定位锚点，用于定义弹出窗口的连接点。默认值为 [bounds](../Anchor/Source/bounds.zh-Hans.md)。
- **arrowEdge**：在 macOS 中定义弹出窗口箭头位置的`attachmentAnchor` 边沿。默认值为[top](../Edge/top.zh-Hans.md)。
- **content**：返回弹出窗口内容的闭包。

## 讨论

当您需要用自定义数据源中的内容显示弹出窗口时，请使用此方法。下面的示例使用`PopoverModel` 结构中的数据来填充`content` 闭合中的视图，弹出窗口将显示给用户：

```swift
struct PopoverExample: View {
    @State private var popover: PopoverModel?

    var body: some View {
        TabView {
            Tab("Popover Anchor", systemImage: "arrow.down") {
                Button("Show Popover") {
                    popover = PopoverModel(message: "Custom Message")
                }
            }
            .popover(item: $popover) { detail in
                 Text("\(detail.message)")
                    .padding()
             }
        }
    }
}

struct PopoverModel: Identifiable {
    var id: String { message }
    let message: String
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/TabContent/popover(item:attachmentAnchor:arrowEdge:content:)
crawled: 2025-12-01T10:50:51Z
---

# popover(item:attachmentAnchor:arrowEdge:content:)

**Instance Method**

Presents a popover using the given item as a data source for the popover’s content.

## Declaration

```swift
nonisolated func popover<Item, Content>(item: Binding<Item?>, attachmentAnchor: PopoverAttachmentAnchor = .rect(.bounds), arrowEdge: Edge? = nil, @ViewBuilder content: @escaping (Item) -> Content) -> some TabContent<Self.TabValue> where Item : Identifiable, Content : View

```

## Parameters

- **item**: A binding to an optional source of truth for the popover. When `item` is non-`nil`, the system passes the contents to the modifier’s closure. You use this content to populate the fields of a popover that you create that the system displays to the user. If `item` changes, the system dismisses the currently presented popover and replaces it with a new popover using the same process.
- **attachmentAnchor**: The positioning anchor that defines the attachment point of the popover. The default is [bounds](../Anchor/Source/bounds.zh-Hans.md).
- **arrowEdge**: The edge of the `attachmentAnchor` that defines the location of the popover’s arrow in macOS. The default is [top](../Edge/top.zh-Hans.md).
- **content**: A closure returning the content of the popover.

## Discussion

Use this method when you need to present a popover with content from a custom data source. The example below uses data in the `PopoverModel` structure to populate the view in the `content` closure that the popover displays to the user:

```swift
struct PopoverExample: View {
    @State private var popover: PopoverModel?

    var body: some View {
        TabView {
            Tab("Popover Anchor", systemImage: "arrow.down") {
                Button("Show Popover") {
                    popover = PopoverModel(message: "Custom Message")
                }
            }
            .popover(item: $popover) { detail in
                 Text("\(detail.message)")
                    .padding()
             }
        }
    }
}

struct PopoverModel: Identifiable {
    var id: String { message }
    let message: String
}
```

