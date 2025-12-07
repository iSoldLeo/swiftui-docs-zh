--- 来源：https://developer.apple.com/documentation/SwiftUI/View/dialogPreventsAppTermination(_:)

抓取时间：2025-11-30T21:08:36Z

---

# dialogPreventsAppTermination(_:)

**实例方法**

此方法用于判断弹出或确认对话框是否会阻止系统或应用终止菜单项退出/终止应用。

## 声明

```swift
nonisolated func dialogPreventsAppTermination(_ prevents: Bool?) -> some View

```

## 讨论

SwiftUI 会根据传递给上述对话框的操作来确定对话框在显示时是否默认阻止应用终止。如果满足以下所有条件，对话框将不会阻止应用程序退出：

- 只有一个按钮，且其角色不是 [destructive](../ButtonRole/destructive.zh-Hans.md)

- [dialogSeverity(_:)](dialogSeverity.zh-Hans.md) 不是 `DialogSeverity/critical``
- There are no [TextField](../TextField.zh-Hans.md)s

Use this modifier after a `View/alert` or `View/confirmationDialog` to specify whether the dialog should prevent app termination. Pass `nil`，以明确请求此修饰符的自动行为/惰性版本。

```swift
struct ConfirmLogoutView: View {
  @State private var isConfirming = false

  var body: some View {
    Button("Logout") { isConfirming = true }
      .confirmationDialog(
        Text("Logout?"),
          isPresented: $isConfirming
        ) {
          Button("Yes") {
            // Handle logout action.
          }
        }
        .dialogPreventsAppTermination(false)
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/dialogPreventsAppTermination(_:)
crawled: 2025-11-30T21:08:36Z
---

# dialogPreventsAppTermination(_:)

**Instance Method**

Whether the alert or confirmation dialog prevents the app from being quit/terminated by the system or app termination menu item.

## Declaration

```swift
nonisolated func dialogPreventsAppTermination(_ prevents: Bool?) -> some View

```

## Discussion

SwiftUI uses the actions passed to the above dialogs to determine whether the dialog should block app termination by default when presented. If all of the following are satisfied, the dialog will not block app quit:

- There is only a single button and its role is not [destructive](../ButtonRole/destructive.zh-Hans.md)
- The [dialogSeverity(_:)](dialogSeverity.zh-Hans.md) is not `DialogSeverity/critical``
- There are no [TextField](../TextField.zh-Hans.md)s

Use this modifier after a `View/alert` or `View/confirmationDialog` to specify whether the dialog should prevent app termination. Pass `nil` to explicitly request the automatic behavior/for the inert version of this modifier.

```swift
struct ConfirmLogoutView: View {
  @State private var isConfirming = false

  var body: some View {
    Button("Logout") { isConfirming = true }
      .confirmationDialog(
        Text("Logout?"),
          isPresented: $isConfirming
        ) {
          Button("Yes") {
            // Handle logout action.
          }
        }
        .dialogPreventsAppTermination(false)
    }
}
```

