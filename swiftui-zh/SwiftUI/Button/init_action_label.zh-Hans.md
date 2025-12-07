--- 来源：https://developer.apple.com/documentation/SwiftUI/Button/init(action:label:)

抓取时间：2025-12-01T02:38:51Z

---

# init(action:label:)

**Initializer**

创建一个显示自定义标签的按钮。

## 声明

```swift
@preconcurrency init(action: @escaping @MainActor () -> Void, @ViewBuilder label: () -> Label)
```

## 参数

- **action**：用户触发按钮时要执行的操作。

- **label**：描述按钮用途的视图。

## 创建按钮

- **init(_:action:)**：创建一个按钮，其标签由本地化字符串键生成。

- **init(_:image:action:)**：创建一个按钮，该按钮的标签由本地化的字符串键和图像资源生成。

- **init(_:systemImage:action:)**：创建一个按钮，该按钮的标签由本地化的字符串键和系统图像名称生成。


---
source: https://developer.apple.com/documentation/SwiftUI/Button/init(action:label:)
crawled: 2025-12-01T02:38:51Z
---

# init(action:label:)

**Initializer**

Creates a button that displays a custom label.

## Declaration

```swift
@preconcurrency init(action: @escaping @MainActor () -> Void, @ViewBuilder label: () -> Label)
```

## Parameters

- **action**: The action to perform when the user triggers the button.
- **label**: A view that describes the purpose of the button’s `action`.

## Creating a button

- **init(_:action:)**: Creates a button that generates its label from a localized string key.
- **init(_:image:action:)**: Creates a button that generates its label from a localized string key and image resource.
- **init(_:systemImage:action:)**: Creates a button that generates its label from a localized string key and system image name.

