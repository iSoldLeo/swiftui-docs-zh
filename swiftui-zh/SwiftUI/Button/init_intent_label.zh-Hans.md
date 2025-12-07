--- 来源：https://developer.apple.com/documentation/SwiftUI/Button/init(intent:label:)

抓取时间：2025-12-01T02:38:58Z

---

# init(intent:label:)

**Initializer**

创建一个按钮，执行 `AppIntent` 操作。

## 声明

```swift
nonisolated init<I>(intent: I, @ViewBuilder label: () -> Label) where I : AppIntent
```

## 参数

- **intent**：要执行的 `AppIntent` 操作。

- **label**：描述按钮 `action` 操作用途的视图。

## 创建按钮以执行应用意图

- **init(_:intent:)**：创建一个按钮，执行 `AppIntent` 操作，并根据本地化字符串键生成其标签。

- **init(_:role:intent:)**：创建一个具有指定角色的按钮，执行 `AppIntent` 操作，并根据字符串生成其标签。

- **init(role:intent:label:)**：创建一个具有指定角色的按钮，执行 `AppIntent` 操作。

- **init(_:image:role:intent:)**：创建一个具有指定角色的按钮，并根据字符串和图像资源生成其标签。

- **init(_:systemImage:role:intent:)**：创建一个具有指定角色的按钮，并根据字符串和系统图像生成其标签。


---
source: https://developer.apple.com/documentation/SwiftUI/Button/init(intent:label:)
crawled: 2025-12-01T02:38:58Z
---

# init(intent:label:)

**Initializer**

Creates a button that performs an `AppIntent`.

## Declaration

```swift
nonisolated init<I>(intent: I, @ViewBuilder label: () -> Label) where I : AppIntent
```

## Parameters

- **intent**: The `AppIntent` to execute.
- **label**: A view that describes the purpose of the button’s `action`.

## Creating a button to perform an App Intent

- **init(_:intent:)**: Creates a button that performs an `AppIntent` and generates its label from a localized string key.
- **init(_:role:intent:)**: Creates a button with a specified role that performs an `AppIntent` and generates its label from a string.
- **init(role:intent:label:)**: Creates a button with a specified role that performs an `AppIntent`.
- **init(_:image:role:intent:)**: Creates a button with a specified role that generates its label from a string and an image resource.
- **init(_:systemImage:role:intent:)**: Creates a button with a specified role that generates its label from a string and a system image.

