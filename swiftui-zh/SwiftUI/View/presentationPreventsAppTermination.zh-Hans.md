--- 来源：https://developer.apple.com/documentation/SwiftUI/View/presentationPreventsAppTermination(_:)

抓取时间：2025-12-02T17:25:09Z

---

# presentationPreventsAppTermination(_:)

**实例方法**

此方法用于判断一个演示文稿是否阻止系统或应用终止菜单项终止/退出应用。

## 声明

```swift
nonisolated func presentationPreventsAppTermination(_ prevents: Bool?) -> some View

```

## 说明

SwiftUI 使用工作表工具栏中的按钮来确定特定工作表是否默认阻止应用终止。如果工具栏中只有一个按钮的 [confirmationAction](../ToolbarItemPlacement/confirmationAction.zh-Hans.md) 或 [cancellationAction](../ToolbarItemPlacement/cancellationAction.zh-Hans.md) 位置，且没有其他工具栏项，则该工作表默认不会阻止应用终止。

使用此修饰符可以指定工作表是否应阻止应用终止。传递 `nil` 以显式请求此修饰符的自动行为/惰性版本。非空值将覆盖 `nil`，并且 `true` 优先于 `false`。

在 `View/sheet` 的 `content` 参数中使用此修饰符。

```swift
struct LaunchScreen: View {
  @State private var presentLogin = false
  var body: some View {
    HomeView()
      .sheet(isPresented: $presentLogin) {
        LoginView()
          // explicitly allow app termination because the
          // default behavior would resolve to `true`.
          .presentationPreventsAppTermination(false)
          .toolbar {
            ToolbarItem(placement: .cancellationAction) {
              Button("Cancel") { presentLogin = false }
            }
            ToolbarItem(placement: .confirmationAction) {
              Button("Login") {
                // Attempt login...
                presentLogin = false
              }
            }
          }
        }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/presentationPreventsAppTermination(_:)
crawled: 2025-12-02T17:25:09Z
---

# presentationPreventsAppTermination(_:)

**Instance Method**

Whether a presentation prevents the app from being terminated/quit by the system or app termination menu item.

## Declaration

```swift
nonisolated func presentationPreventsAppTermination(_ prevents: Bool?) -> some View

```

## Discussion

SwiftUI uses the buttons in a sheet’s toolbar to determine whether a particular sheet should block termination by default. If there is a singular toolbar item with the [confirmationAction](../ToolbarItemPlacement/confirmationAction.zh-Hans.md) or the [cancellationAction](../ToolbarItemPlacement/cancellationAction.zh-Hans.md) placement and no other toolbar items, the sheet will not prevent termination by default.

Use this modifier to specify whether a sheet should prevent app termination. Pass `nil` to explicitly request the automatic behavior/for the inert version of this modifier. Non-nil values will override `nil`, and `true` takes precedence over `false`.

Use this modifier within the `content` argument to `View/sheet`

```swift
struct LaunchScreen: View {
  @State private var presentLogin = false
  var body: some View {
    HomeView()
      .sheet(isPresented: $presentLogin) {
        LoginView()
          // explicitly allow app termination because the
          // default behavior would resolve to `true`.
          .presentationPreventsAppTermination(false)
          .toolbar {
            ToolbarItem(placement: .cancellationAction) {
              Button("Cancel") { presentLogin = false }
            }
            ToolbarItem(placement: .confirmationAction) {
              Button("Login") {
                // Attempt login...
                presentLogin = false
              }
            }
          }
        }
    }
}
```

