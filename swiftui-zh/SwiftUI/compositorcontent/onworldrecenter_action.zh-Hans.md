--- 来源：https://developer.apple.com/documentation/swiftui/compositorcontent/onworldrecenter(action:)

抓取时间：2025-12-01T11:21:50Z

---

# onWorldRecenter(action:)

**实例方法**

添加一个在使用数码表冠重新定位视图时要执行的操作。

## 声明

```swift
nonisolated func onWorldRecenter(action: @escaping @MainActor () -> Void) -> some CompositorContent

```

## 参数

- **action**：一个在内容重新定位时运行的闭包。当应用重新定位并即将淡入时，此闭包将运行，等效于 `WorldRecenterPhase.ended`。

## 说明

当用户重新定位内容时，应用会淡出，然后重新定位。重新定位后，将执行相应操作，应用将淡入显示。如果应用未在后台运行或处于暂停状态，则会执行此操作。


---
source: https://developer.apple.com/documentation/swiftui/compositorcontent/onworldrecenter(action:)
crawled: 2025-12-01T11:21:50Z
---

# onWorldRecenter(action:)

**Instance Method**

Adds an action to perform when recentering the view with the digital crown.

## Declaration

```swift
nonisolated func onWorldRecenter(action: @escaping @MainActor () -> Void) -> some CompositorContent

```

## Parameters

- **action**: A closure to run when the content is recentered. This will run when the app has been recentered and is about to fade back in, equivalent to `WorldRecenterPhase.ended`.

## Discussion

When the user recenters their content, the app will fade out and then be repositioned. Once it has been repositioned, the action will be called and the app will fade back in. The action will be called if the app is not backgrounded or suspended.

