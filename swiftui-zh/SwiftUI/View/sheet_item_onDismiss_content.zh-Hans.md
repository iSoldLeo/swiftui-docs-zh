--- 来源：https://developer.apple.com/documentation/SwiftUI/View/sheet(item:onDismiss:content:)

抓取时间：2025-11-30T21:15:05Z

---

# sheet(item:onDismiss:content:)

**实例方法**

使用给定的 item 作为工作表内容的数据源来呈现工作表。

## 声明

```swift
nonisolated func sheet<Item, Content>(item: Binding<Item?>, onDismiss: (() -> Void)? = nil, @ViewBuilder content: @escaping (Item) -> Content) -> some View where Item : Identifiable, Content : View

```

## 参数

- **item**：指向工作表可选数据源的绑定。当 `item` 不为 `nil` 时，系统会将 item 的内容传递给修饰符的闭包。您可以在自己创建的、系统会显示给用户的表格中显示此内容。如果 `item` 发生更改，系统将关闭当前工作表，并使用相同的流程将其替换为新的工作表。

- **onDismiss**：关闭工作表时要执行的闭包。

- **content**：返回工作表内容的闭包。

## 讨论

当您需要使用来自自定义数据源的内容来呈现模态视图时，请使用此方法。以下示例展示了自定义数据源 `InventoryItem`，`content` 闭包使用该数据源来填充操作表向用户显示的显示内容：

```swift
struct ShowPartDetail: View {
    @State private var sheetDetail: InventoryItem?

    var body: some View {
        Button("Show Part Details") {
            sheetDetail = InventoryItem(
                id: "0123456789",
                partNumber: "Z-1234A",
                quantity: 100,
                name: "Widget")
        }
        .sheet(item: $sheetDetail,
               onDismiss: didDismiss) { detail in
            VStack(alignment: .leading, spacing: 20) {
                Text("Part Number: \(detail.partNumber)")
                Text("Name: \(detail.name)")
                Text("Quantity On-Hand: \(detail.quantity)")
            }
            .onTapGesture {
                sheetDetail = nil
            }
        }
    }

    func didDismiss() {
        // Handle the dismissing action.
    }
}

struct InventoryItem: Identifiable {
    var id: String
    let partNumber: String
    let quantity: Int
    let name: String
}
```

在垂直紧凑的环境中，例如横屏模式下的 iPhone，工作表会自动调整以全屏封面的形式显示。使用 [presentationCompactAdaptation(_:)](presentationCompactAdaptation.zh-Hans.md) 或 [presentationCompactAdaptation(horizontal:vertical:)](presentationCompactAdaptation_horizontal_vertical.zh-Hans.md) 修饰符可以覆盖此行为。

### 穿透效果

在 visionOS 中，大多数系统演示默认带有穿透效果。要更改外层演示穿透遮挡内容的方式，请使用 [presentationBreakthroughEffect(_:)](presentationBreakthroughEffect.zh-Hans.md)，如下例所示：

```swift
.sheet(item: $sheetDetail,
       onDismiss: didDismiss) { detail in
    VStack(alignment: .leading, spacing: 20) {
        Text("Part Number: \(detail.partNumber)")
        Text("Name: \(detail.name)")
        Text("Quantity On-Hand: \(detail.quantity)")
    }
    .presentationBreakthroughEffect(.prominent)
    .onTapGesture {
        sheetDetail = nil
    }
}
```

## 显示工作表、封面或弹出框

- **sheet(isPresented:onDismiss:content:)**：当绑定到您提供的布尔值且该值为真时，显示一个工作表。

- **fullScreenCover(isPresented:onDismiss:content:)**：当绑定到您提供的布尔值且该值为真时，显示一个尽可能覆盖屏幕的模态视图。

- **fullScreenCover(item:onDismiss:content:)**：使用您提供的绑定作为工作表内容的数据源，显示一个尽可能覆盖屏幕的模态视图。

- **popover(item:attachmentAnchor:arrowEdge:content:)**：使用给定项作为弹出框内容的数据源，显示一个弹出框。

- **popover(isPresented:attachmentAnchor:arrowEdge:content:)**：当给定条件为真时，显示一个弹出框。

- **PopoverAttachmentAnchor**：弹出框的附件锚点。


---
source: https://developer.apple.com/documentation/SwiftUI/View/sheet(item:onDismiss:content:)
crawled: 2025-11-30T21:15:05Z
---

# sheet(item:onDismiss:content:)

**Instance Method**

Presents a sheet using the given item as a data source for the sheet’s content.

## Declaration

```swift
nonisolated func sheet<Item, Content>(item: Binding<Item?>, onDismiss: (() -> Void)? = nil, @ViewBuilder content: @escaping (Item) -> Content) -> some View where Item : Identifiable, Content : View

```

## Parameters

- **item**: A binding to an optional source of truth for the sheet. When `item` is non-`nil`, the system passes the item’s content to the modifier’s closure. You display this content in a sheet that you create that the system displays to the user. If `item` changes, the system dismisses the sheet and replaces it with a new one using the same process.
- **onDismiss**: The closure to execute when dismissing the sheet.
- **content**: A closure returning the content of the sheet.

## Discussion

Use this method when you need to present a modal view with content from a custom data source. The example below shows a custom data source `InventoryItem` that the `content` closure uses to populate the display the action sheet shows to the user:

```swift
struct ShowPartDetail: View {
    @State private var sheetDetail: InventoryItem?

    var body: some View {
        Button("Show Part Details") {
            sheetDetail = InventoryItem(
                id: "0123456789",
                partNumber: "Z-1234A",
                quantity: 100,
                name: "Widget")
        }
        .sheet(item: $sheetDetail,
               onDismiss: didDismiss) { detail in
            VStack(alignment: .leading, spacing: 20) {
                Text("Part Number: \(detail.partNumber)")
                Text("Name: \(detail.name)")
                Text("Quantity On-Hand: \(detail.quantity)")
            }
            .onTapGesture {
                sheetDetail = nil
            }
        }
    }

    func didDismiss() {
        // Handle the dismissing action.
    }
}

struct InventoryItem: Identifiable {
    var id: String
    let partNumber: String
    let quantity: Int
    let name: String
}
```



In vertically compact environments, such as iPhone in landscape orientation, a sheet presentation automatically adapts to appear as a full-screen cover. Use the [presentationCompactAdaptation(_:)](presentationCompactAdaptation.zh-Hans.md) or [presentationCompactAdaptation(horizontal:vertical:)](presentationCompactAdaptation_horizontal_vertical.zh-Hans.md) modifier to override this behavior.

### Breakthrough effect

In visionOS, most system presentations appear with a breakthrough effect by default. To change how the enclosing presentation breaks through content occluding it, use [presentationBreakthroughEffect(_:)](presentationBreakthroughEffect.zh-Hans.md), like in the following example:

```swift
.sheet(item: $sheetDetail,
       onDismiss: didDismiss) { detail in
    VStack(alignment: .leading, spacing: 20) {
        Text("Part Number: \(detail.partNumber)")
        Text("Name: \(detail.name)")
        Text("Quantity On-Hand: \(detail.quantity)")
    }
    .presentationBreakthroughEffect(.prominent)
    .onTapGesture {
        sheetDetail = nil
    }
}
```



## Showing a sheet, cover, or popover

- **sheet(isPresented:onDismiss:content:)**: Presents a sheet when a binding to a Boolean value that you provide is true.
- **fullScreenCover(isPresented:onDismiss:content:)**: Presents a modal view that covers as much of the screen as possible when binding to a Boolean value you provide is true.
- **fullScreenCover(item:onDismiss:content:)**: Presents a modal view that covers as much of the screen as possible using the binding you provide as a data source for the sheet’s content.
- **popover(item:attachmentAnchor:arrowEdge:content:)**: Presents a popover using the given item as a data source for the popover’s content.
- **popover(isPresented:attachmentAnchor:arrowEdge:content:)**: Presents a popover when a given condition is true.
- **PopoverAttachmentAnchor**: An attachment anchor for a popover.

