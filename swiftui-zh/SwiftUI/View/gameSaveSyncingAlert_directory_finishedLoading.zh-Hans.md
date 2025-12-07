--- 来源：https://developer.apple.com/documentation/SwiftUI/View/gameSaveSyncingAlert(directory:finishedLoading:)

抓取时间：2025-12-02T17:23:47Z

---

# gameSaveSyncingAlert(directory:finishedLoading:)

**实例方法**

在游戏同步目录加载期间显示模态视图。

## 声明

```swift
@MainActor @preconcurrency func gameSaveSyncingAlert(directory: Binding<GameSaveSyncedDirectory?>, finishedLoading: @escaping @MainActor () -> Void) -> some View

```

## 参数

- **directory**：绑定到可选的游戏同步目录，该目录由调用 `GameSaveSyncedDirectory/openDirectory(containerIdentifier:)` 返回。如果此值为 `nil`，则不显示视图。

- **finishedLoading**：加载过程完成后要执行的闭包。

## 讨论

当您提供的布尔值为真时，如果希望向用户显示模态加载视图，请使用此方法。


---
source: https://developer.apple.com/documentation/SwiftUI/View/gameSaveSyncingAlert(directory:finishedLoading:)
crawled: 2025-12-02T17:23:47Z
---

# gameSaveSyncingAlert(directory:finishedLoading:)

**Instance Method**

Presents a modal view while the game synced directory loads.

## Declaration

```swift
@MainActor @preconcurrency func gameSaveSyncingAlert(directory: Binding<GameSaveSyncedDirectory?>, finishedLoading: @escaping @MainActor () -> Void) -> some View

```

## Parameters

- **directory**: A binding to an optional game synced directory that was returned by calling `GameSaveSyncedDirectory/openDirectory(containerIdentifier:)`. If this value is `nil`, the view doesn’t display.
- **finishedLoading**: The closure to execute after the loading process completes.

## Discussion

Use this method when you want to present a modal loading view to the user when a Boolean value you provide is true.

