--- 来源：https://developer.apple.com/documentation/SwiftUI/View/fullScreenCover(item:onDismiss:content:)

抓取时间：2025-11-30T21:15:05Z

---

# fullScreenCover(item:onDismiss:content:)

**实例方法**

使用您提供的绑定作为工作表内容的数据源，呈现一个尽可能覆盖屏幕的模态视图。

## 声明

```swift
nonisolated func fullScreenCover<Item, Content>(item: Binding<Item?>, onDismiss: (() -> Void)? = nil, @ViewBuilder content: @escaping (Item) -> Content) -> some View where Item : Identifiable, Content : View

```

## 参数

- **item**：指向工作表可选数据源的绑定。当 `item` 不为 `nil` 时，系统会将内容传递给修饰符的闭包。您可以创建并向用户显示此内容的工作表。如果 `item` 发生更改，系统将关闭当前显示的工作表，并使用相同的流程将其替换为新的工作表。

- **onDismiss**：关闭模态视图时要执行的闭包。

- **content**：返回模态视图内容的闭包。

## 讨论

使用此方法显示尽可能覆盖屏幕的模态视图。在以下示例中，自定义结构 — `CoverData` — 为用户点击或轻触“显示带数据的全屏封面”按钮时，`content` 闭包中显示的全屏视图提供数据：

```swift
struct FullScreenCoverItemOnDismissContent: View {
    @State private var coverData: CoverData?

    var body: some View {
        Button("Present Full-Screen Cover With Data") {
            coverData = CoverData(body: "Custom Data")
        }
        .fullScreenCover(item: $coverData,
                         onDismiss: didDismiss) { details in
            VStack(spacing: 20) {
                Text("\(details.body)")
            }
            .onTapGesture {
                coverData = nil
            }
        }
    }

    func didDismiss() {
        // Handle the dismissing action.
    }

}

struct CoverData: Identifiable {
    var id: String {
        return body
    }
    let body: String
}
```

## 显示工作表、封面或弹出框

- **sheet(isPresented:onDismiss:content:)**：当绑定到您提供的布尔值且该值为真时，显示一个工作表。

- **sheet(item:onDismiss:content:)**：使用给定项作为工作表内容的数据源来显示工作表。

- **fullScreenCover(isPresented:onDismiss:content:)**：当绑定到您提供的布尔值且该值为真时，显示一个尽可能覆盖屏幕的模态视图。

- **popover(item:attachmentAnchor:arrowEdge:content:)**：使用指定项目作为弹出框内容的数据源来显示弹出框。

- **popover(isPresented:attachmentAnchor:arrowEdge:content:)**：当满足指定条件时显示弹出框。

- **PopoverAttachmentAnchor**：弹出框的附件锚点。


---
source: https://developer.apple.com/documentation/SwiftUI/View/fullScreenCover(item:onDismiss:content:)
crawled: 2025-11-30T21:15:05Z
---

# fullScreenCover(item:onDismiss:content:)

**Instance Method**

Presents a modal view that covers as much of the screen as possible using the binding you provide as a data source for the sheet’s content.

## Declaration

```swift
nonisolated func fullScreenCover<Item, Content>(item: Binding<Item?>, onDismiss: (() -> Void)? = nil, @ViewBuilder content: @escaping (Item) -> Content) -> some View where Item : Identifiable, Content : View

```

## Parameters

- **item**: A binding to an optional source of truth for the sheet. When `item` is non-`nil`, the system passes the contents to the modifier’s closure. You display this content in a sheet that you create that the system displays to the user. If `item` changes, the system dismisses the currently displayed sheet and replaces it with a new one using the same process.
- **onDismiss**: The closure to execute when dismissing the modal view.
- **content**: A closure returning the content of the modal view.

## Discussion

Use this method to display a modal view that covers as much of the screen as possible. In the example below a custom structure — `CoverData` — provides data for the full-screen view to display in the `content` closure when the user clicks or taps the “Present Full-Screen Cover With Data” button:

```swift
struct FullScreenCoverItemOnDismissContent: View {
    @State private var coverData: CoverData?

    var body: some View {
        Button("Present Full-Screen Cover With Data") {
            coverData = CoverData(body: "Custom Data")
        }
        .fullScreenCover(item: $coverData,
                         onDismiss: didDismiss) { details in
            VStack(spacing: 20) {
                Text("\(details.body)")
            }
            .onTapGesture {
                coverData = nil
            }
        }
    }

    func didDismiss() {
        // Handle the dismissing action.
    }

}

struct CoverData: Identifiable {
    var id: String {
        return body
    }
    let body: String
}
```



## Showing a sheet, cover, or popover

- **sheet(isPresented:onDismiss:content:)**: Presents a sheet when a binding to a Boolean value that you provide is true.
- **sheet(item:onDismiss:content:)**: Presents a sheet using the given item as a data source for the sheet’s content.
- **fullScreenCover(isPresented:onDismiss:content:)**: Presents a modal view that covers as much of the screen as possible when binding to a Boolean value you provide is true.
- **popover(item:attachmentAnchor:arrowEdge:content:)**: Presents a popover using the given item as a data source for the popover’s content.
- **popover(isPresented:attachmentAnchor:arrowEdge:content:)**: Presents a popover when a given condition is true.
- **PopoverAttachmentAnchor**: An attachment anchor for a popover.

