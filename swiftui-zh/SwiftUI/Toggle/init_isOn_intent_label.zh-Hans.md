---
来源：https://developer.apple.com/documentation/SwiftUI/Toggle/init(isOn:intent:label:)
抓取时间：2025-12-01T02:45:33Z
---

# init(isOn:intent:label:)

**Initializer**

创建一个执行`AppIntent`的切换器。

### 声明

```swift
nonisolated init<I>(isOn: Bool, intent: I, @ViewBuilder label: () -> Label) where I : AppIntent
```

## 参数

- **isOn**：切换是打开还是关闭。
- **intent**：要执行的`AppIntent`。
- **label**：描述切换目的的视图。

## 为应用程序意图创建切换按钮

- **init(_:isOn:intent:)**：创建一个执行`AppIntent` 的切换，并通过本地化字符串键生成其标签。


---
source: https://developer.apple.com/documentation/SwiftUI/Toggle/init(isOn:intent:label:)
crawled: 2025-12-01T02:45:33Z
---

# init(isOn:intent:label:)

**Initializer**

Creates a toggle performing an `AppIntent`.

## Declaration

```swift
nonisolated init<I>(isOn: Bool, intent: I, @ViewBuilder label: () -> Label) where I : AppIntent
```

## Parameters

- **isOn**: Whether the toggle is on or off.
- **intent**: The `AppIntent` to be performed.
- **label**: A view that describes the purpose of the toggle.

## Creating a toggle for an App Intent

- **init(_:isOn:intent:)**: Creates a toggle performing an `AppIntent` and generates its label from a localized string key.

