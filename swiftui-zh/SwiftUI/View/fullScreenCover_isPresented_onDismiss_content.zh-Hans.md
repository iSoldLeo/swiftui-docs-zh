--- 来源：https://developer.apple.com/documentation/SwiftUI/View/fullScreenCover(isPresented:onDismiss:content:)

抓取时间：2025-12-02T16:23:40Z

---

# fullScreenCover(isPresented:onDismiss:content:)

**实例方法**

当绑定到您提供的布尔值为真时，显示一个尽可能覆盖屏幕的模态视图。

## 声明

```swift
nonisolated func fullScreenCover<Content>(isPresented: Binding<Bool>, onDismiss: (() -> Void)? = nil, @ViewBuilder content: @escaping () -> Content) -> some View where Content : View

```

## 参数

- **isPresented**：绑定到一个布尔值，用于确定是否显示该视图。

- **onDismiss**：关闭模态视图时要执行的闭包。

- **content**：返回模态视图内容的闭包。

## 讨论

使用此方法显示尽可能覆盖屏幕的模态视图。以下示例在用户切换 `isPresenting` 绑定的值时显示自定义视图：

```swift
struct FullScreenCoverPresentedOnDismiss: View {
    @State private var isPresenting = false
    var body: some View {
        Button("Present Full-Screen Cover") {
            isPresenting.toggle()
        }
        .fullScreenCover(isPresented: $isPresenting,
                         onDismiss: didDismiss) {
            VStack {
                Text("A full-screen modal view.")
                    .font(.title)
                Text("Tap to Dismiss")
            }
            .onTapGesture {
                isPresenting.toggle()
            }
            .foregroundColor(.white)
            .frame(maxWidth: .infinity,
                   maxHeight: .infinity)
            .background(Color.blue)
            .ignoresSafeArea(edges: .all)
        }
    }

    func didDismiss() {
        // Handle the dismissing action.
    }
}
```

## 显示工作表、封面或弹出框

- **sheet(isPresented:onDismiss:content:)**：当您提供的布尔值绑定为真时，显示工作表。

- **sheet(item:onDismiss:content:)**：使用给定项作为工作表内容的数据源来显示工作表。

- **fullScreenCover(item:onDismiss:content:)**：使用您提供的绑定作为工作表内容的数据源，显示尽可能覆盖屏幕的模态视图。

- **popover(item:attachmentAnchor:arrowEdge:content:)**：使用指定项目作为弹出框内容的数据源来显示弹出框。

- **popover(isPresented:attachmentAnchor:arrowEdge:content:)**：当满足指定条件时显示弹出框。

- **PopoverAttachmentAnchor**：弹出框的附件锚点。


---
source: https://developer.apple.com/documentation/SwiftUI/View/fullScreenCover(isPresented:onDismiss:content:)
crawled: 2025-12-02T16:23:40Z
---

# fullScreenCover(isPresented:onDismiss:content:)

**Instance Method**

Presents a modal view that covers as much of the screen as possible when binding to a Boolean value you provide is true.

## Declaration

```swift
nonisolated func fullScreenCover<Content>(isPresented: Binding<Bool>, onDismiss: (() -> Void)? = nil, @ViewBuilder content: @escaping () -> Content) -> some View where Content : View

```

## Parameters

- **isPresented**: A binding to a Boolean value that determines whether to present the sheet.
- **onDismiss**: The closure to execute when dismissing the modal view.
- **content**: A closure that returns the content of the modal view.

## Discussion

Use this method to show a modal view that covers as much of the screen as possible. The example below displays a custom view when the user toggles the value of the `isPresenting` binding:

```swift
struct FullScreenCoverPresentedOnDismiss: View {
    @State private var isPresenting = false
    var body: some View {
        Button("Present Full-Screen Cover") {
            isPresenting.toggle()
        }
        .fullScreenCover(isPresented: $isPresenting,
                         onDismiss: didDismiss) {
            VStack {
                Text("A full-screen modal view.")
                    .font(.title)
                Text("Tap to Dismiss")
            }
            .onTapGesture {
                isPresenting.toggle()
            }
            .foregroundColor(.white)
            .frame(maxWidth: .infinity,
                   maxHeight: .infinity)
            .background(Color.blue)
            .ignoresSafeArea(edges: .all)
        }
    }

    func didDismiss() {
        // Handle the dismissing action.
    }
}
```



## Showing a sheet, cover, or popover

- **sheet(isPresented:onDismiss:content:)**: Presents a sheet when a binding to a Boolean value that you provide is true.
- **sheet(item:onDismiss:content:)**: Presents a sheet using the given item as a data source for the sheet’s content.
- **fullScreenCover(item:onDismiss:content:)**: Presents a modal view that covers as much of the screen as possible using the binding you provide as a data source for the sheet’s content.
- **popover(item:attachmentAnchor:arrowEdge:content:)**: Presents a popover using the given item as a data source for the popover’s content.
- **popover(isPresented:attachmentAnchor:arrowEdge:content:)**: Presents a popover when a given condition is true.
- **PopoverAttachmentAnchor**: An attachment anchor for a popover.

