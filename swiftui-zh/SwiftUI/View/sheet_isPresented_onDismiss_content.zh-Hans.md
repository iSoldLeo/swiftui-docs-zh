--- 来源：https://developer.apple.com/documentation/SwiftUI/View/sheet(isPresented:onDismiss:content:)

抓取时间：2025-12-02T17:30:03Z

---

# sheet(isPresented:onDismiss:content:)

**实例方法**

当您提供的布尔值绑定为真时，显示一个工作表。

## 声明

```swift
nonisolated func sheet<Content>(isPresented: Binding<Bool>, onDismiss: (() -> Void)? = nil, @ViewBuilder content: @escaping () -> Content) -> some View where Content : View

```

## 参数

- **isPresented**：绑定到一个布尔值，该值决定是否显示您在修饰符的闭包中创建的工作表。`content`

- **onDismiss**：关闭工作表时要执行的闭包。

- **content**：返回工作表内容的闭包。

## 讨论

当您希望在提供的布尔值为真时向用户显示模态视图时，请使用此方法。以下示例在用户点击或轻触“显示许可协议”按钮切换 `isShowingSheet` 变量时，显示软件许可协议模型的模态视图：

```swift
struct ShowLicenseAgreement: View {
    @State private var isShowingSheet = false
    var body: some View {
        Button(action: {
            isShowingSheet.toggle()
        }) {
            Text("Show License Agreement")
        }
        .sheet(isPresented: $isShowingSheet,
               onDismiss: didDismiss) {
            VStack {
                Text("License Agreement")
                    .font(.title)
                    .padding(50)
                Text("""
                        Terms and conditions go here.
                    """)
                    .padding(50)
                Button("Dismiss",
                       action: { isShowingSheet.toggle() })
            }
        }
    }

    func didDismiss() {
        // Handle the dismissing action.
    }
}
```

在垂直紧凑的环境中，例如横屏模式下的 iPhone，工作表演示会自动调整为全屏显示。使用 [presentationCompactAdaptation(_:)](presentationCompactAdaptation.zh-Hans.md) 或 [presentationCompactAdaptation(horizontal:vertical:)](presentationCompactAdaptation_horizontal_vertical.zh-Hans.md) 修饰符可以覆盖此行为。

### 突破效果

在 visionOS 中，大多数系统演示默认以突破效果显示。要更改外层视图穿透遮挡内容的方式，请使用 [presentationBreakthroughEffect(_:)](presentationBreakthroughEffect.zh-Hans.md)，如下例所示：

```swift
.sheet(isPresented: $isShowingSheet,
       onDismiss: didDismiss) {
    VStack {
        Text("License Agreement")
            .font(.title)
            .padding(50)
        Text("""
                Terms and conditions go here.
            """)
            .padding(50)
        Button("Dismiss",
               action: { isShowingSheet.toggle() })
    }
    .presentationBreakthroughEffect(.prominent)
}
```

## 显示工作表、封面或弹出框

- **sheet(item:onDismiss:content:)**：使用指定项作为工作表内容的数据源来显示工作表。

- **fullScreenCover(isPresented:onDismiss:content:)**：当绑定到您提供的布尔值为真时，显示一个尽可能覆盖屏幕的模态视图。

- **fullScreenCover(item:onDismiss:content:)**：使用您提供的绑定作为工作表内容的数据源来显示一个尽可能覆盖屏幕的模态视图。

- **popover(item:attachmentAnchor:arrowEdge:content:)**：使用指定项作为弹出框内容的数据源来显示弹出框。

- **popover(isPresented:attachmentAnchor:arrowEdge:content:)**：当满足特定条件时，显示弹出窗口。

- **PopoverAttachmentAnchor**：弹出窗口的附件锚点。


---
source: https://developer.apple.com/documentation/SwiftUI/View/sheet(isPresented:onDismiss:content:)
crawled: 2025-12-02T17:30:03Z
---

# sheet(isPresented:onDismiss:content:)

**Instance Method**

Presents a sheet when a binding to a Boolean value that you provide is true.

## Declaration

```swift
nonisolated func sheet<Content>(isPresented: Binding<Bool>, onDismiss: (() -> Void)? = nil, @ViewBuilder content: @escaping () -> Content) -> some View where Content : View

```

## Parameters

- **isPresented**: A binding to a Boolean value that determines whether to present the sheet that you create in the modifier’s `content` closure.
- **onDismiss**: The closure to execute when dismissing the sheet.
- **content**: A closure that returns the content of the sheet.

## Discussion

Use this method when you want to present a modal view to the user when a Boolean value you provide is true. The example below displays a modal view of the mockup for a software license agreement when the user toggles the `isShowingSheet` variable by clicking or tapping on the “Show License Agreement” button:

```swift
struct ShowLicenseAgreement: View {
    @State private var isShowingSheet = false
    var body: some View {
        Button(action: {
            isShowingSheet.toggle()
        }) {
            Text("Show License Agreement")
        }
        .sheet(isPresented: $isShowingSheet,
               onDismiss: didDismiss) {
            VStack {
                Text("License Agreement")
                    .font(.title)
                    .padding(50)
                Text("""
                        Terms and conditions go here.
                    """)
                    .padding(50)
                Button("Dismiss",
                       action: { isShowingSheet.toggle() })
            }
        }
    }

    func didDismiss() {
        // Handle the dismissing action.
    }
}
```



In vertically compact environments, such as iPhone in landscape orientation, a sheet presentation automatically adapts to appear as a full-screen cover. Use the [presentationCompactAdaptation(_:)](presentationCompactAdaptation.zh-Hans.md) or [presentationCompactAdaptation(horizontal:vertical:)](presentationCompactAdaptation_horizontal_vertical.zh-Hans.md) modifier to override this behavior.

### Breakthrough effect

In visionOS, most system presentations appear with a breakthrough effect by default. To change how the enclosing presentation breaks through content occluding it, use [presentationBreakthroughEffect(_:)](presentationBreakthroughEffect.zh-Hans.md), like in the following example:

```swift
.sheet(isPresented: $isShowingSheet,
       onDismiss: didDismiss) {
    VStack {
        Text("License Agreement")
            .font(.title)
            .padding(50)
        Text("""
                Terms and conditions go here.
            """)
            .padding(50)
        Button("Dismiss",
               action: { isShowingSheet.toggle() })
    }
    .presentationBreakthroughEffect(.prominent)
}
```



## Showing a sheet, cover, or popover

- **sheet(item:onDismiss:content:)**: Presents a sheet using the given item as a data source for the sheet’s content.
- **fullScreenCover(isPresented:onDismiss:content:)**: Presents a modal view that covers as much of the screen as possible when binding to a Boolean value you provide is true.
- **fullScreenCover(item:onDismiss:content:)**: Presents a modal view that covers as much of the screen as possible using the binding you provide as a data source for the sheet’s content.
- **popover(item:attachmentAnchor:arrowEdge:content:)**: Presents a popover using the given item as a data source for the popover’s content.
- **popover(isPresented:attachmentAnchor:arrowEdge:content:)**: Presents a popover when a given condition is true.
- **PopoverAttachmentAnchor**: An attachment anchor for a popover.

