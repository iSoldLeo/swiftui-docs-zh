--- 来源：https://developer.apple.com/documentation/SwiftUI/View/alert(isPresented:content:)

抓取时间：2025-12-03T05:35:55Z

---

# alert(isPresented:content:)

**实例方法**

向用户显示一个提示框。

## 声明

```swift
nonisolated func alert(isPresented: Binding<Bool>, content: () -> Alert) -> some View

```

## 参数

- **isPresented**：绑定到一个布尔值，该值决定是否显示您在修饰符的闭包中创建的提示框。当用户按下或点击“确定”时，系统会将 `isPresented` 设置为 `false`，从而关闭提示框。

- **content**：返回要显示的提示框的闭包。

## 讨论

当需要向用户显示提示框时，请使用此方法。以下示例显示了一个提示框，当用户切换控制提示框显示方式的布尔值时，该提示框就会显示：

```swift
struct OrderCompleteAlert: View {
    @State private var isPresented = false
    var body: some View {
        Button("Show Alert", action: {
            isPresented = true
        })
        .alert(isPresented: $isPresented) {
            Alert(title: Text("Order Complete"),
                  message: Text("Thank you for shopping with us."),
                  dismissButton: .default(Text("OK")))
        }
    }
}
```

## 视图显示修饰符

- **actionSheet(isPresented:content:)**：当给定条件为真时，显示操作表。

- **actionSheet(item:content:)**：使用给定项作为操作表内容的数据源，显示操作表。

- **alert(item:content:)**：向用户显示提示框。


---
source: https://developer.apple.com/documentation/SwiftUI/View/alert(isPresented:content:)
crawled: 2025-12-03T05:35:55Z
---

# alert(isPresented:content:)

**Instance Method**

Presents an alert to the user.

## Declaration

```swift
nonisolated func alert(isPresented: Binding<Bool>, content: () -> Alert) -> some View

```

## Parameters

- **isPresented**: A binding to a Boolean value that determines whether to present the alert that you create in the modifier’s `content` closure. When the user presses or taps OK the system sets `isPresented` to `false` which dismisses the alert.
- **content**: A closure returning the alert to present.

## Discussion

Use this method when you need to show an alert to the user. The example below displays an alert that is shown when the user toggles a Boolean value that controls the presentation of the alert:

```swift
struct OrderCompleteAlert: View {
    @State private var isPresented = false
    var body: some View {
        Button("Show Alert", action: {
            isPresented = true
        })
        .alert(isPresented: $isPresented) {
            Alert(title: Text("Order Complete"),
                  message: Text("Thank you for shopping with us."),
                  dismissButton: .default(Text("OK")))
        }
    }
}
```



## View presentation modifiers

- **actionSheet(isPresented:content:)**: Presents an action sheet when a given condition is true.
- **actionSheet(item:content:)**: Presents an action sheet using the given item as a data source for the sheet’s content.
- **alert(item:content:)**: Presents an alert to the user.

