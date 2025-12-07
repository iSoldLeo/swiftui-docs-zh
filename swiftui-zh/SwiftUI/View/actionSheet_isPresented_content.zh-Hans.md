--- 来源：https://developer.apple.com/documentation/SwiftUI/View/actionSheet(isPresented:content:)

抓取时间：2025-12-03T05:35:54Z

---

# actionSheet(isPresented:content:)

**实例方法**

当给定条件为真时，显示操作表。

## 声明

```swift
nonisolated func actionSheet(isPresented: Binding<Bool>, content: () -> ActionSheet) -> some View

```

## 参数

- **isPresented**：绑定到一个布尔值，该值决定是否显示您在修饰符的闭包中创建的操作表。`content` 当用户按下或点击操作表的默认操作按钮时，系统会将此值设置为 `false` 以关闭操作表。

- **content**：返回 `ActionSheet` 的闭包。

## 讨论

在下面的示例中，按钮会根据绑定的布尔变量的值有条件地显示一个操作表。当布尔值设置为 `true` 时，系统会显示一个包含破坏性操作和默认操作的操作表：

```swift
struct ConfirmEraseItems: View {
    @State private var isShowingSheet = false
    var body: some View {
        Button("Show Action Sheet", action: {
            isShowingSheet = true
        })
        .actionSheet(isPresented: $isShowingSheet) {
            ActionSheet(
                title: Text("Permanently erase the items in the Trash?"),
                message: Text("You can't undo this action."),
                buttons:[
                    .destructive(Text("Empty Trash"),
                                 action: emptyTrashAction),
                    .cancel()
                ]
            )}
    }

    func emptyTrashAction() {
        // Handle empty trash action.
    }
}
```

## 视图显示修饰符

- **actionSheet(item:content:)**：使用给定项作为操作表内容的数据源来显示操作表。

- **alert(isPresented:content:)**：向用户显示一个警告。

- **alert(item:content:)**：向用户显示一个警告。


---
source: https://developer.apple.com/documentation/SwiftUI/View/actionSheet(isPresented:content:)
crawled: 2025-12-03T05:35:54Z
---

# actionSheet(isPresented:content:)

**Instance Method**

Presents an action sheet when a given condition is true.

## Declaration

```swift
nonisolated func actionSheet(isPresented: Binding<Bool>, content: () -> ActionSheet) -> some View

```

## Parameters

- **isPresented**: A binding to a Boolean value that determines whether to present the action sheet that you create in the modifier’s `content` closure. When the user presses or taps the sheet’s default action button the system sets this value to `false` dismissing the sheet.
- **content**: A closure returning the `ActionSheet` to present.

## Discussion

In the example below, a button conditionally presents an action sheet depending upon the value of a bound Boolean variable. When the Boolean value is set to `true`, the system displays an action sheet with both destructive and default actions:

```swift
struct ConfirmEraseItems: View {
    @State private var isShowingSheet = false
    var body: some View {
        Button("Show Action Sheet", action: {
            isShowingSheet = true
        })
        .actionSheet(isPresented: $isShowingSheet) {
            ActionSheet(
                title: Text("Permanently erase the items in the Trash?"),
                message: Text("You can't undo this action."),
                buttons:[
                    .destructive(Text("Empty Trash"),
                                 action: emptyTrashAction),
                    .cancel()
                ]
            )}
    }

    func emptyTrashAction() {
        // Handle empty trash action.
    }
}
```





## View presentation modifiers

- **actionSheet(item:content:)**: Presents an action sheet using the given item as a data source for the sheet’s content.
- **alert(isPresented:content:)**: Presents an alert to the user.
- **alert(item:content:)**: Presents an alert to the user.

