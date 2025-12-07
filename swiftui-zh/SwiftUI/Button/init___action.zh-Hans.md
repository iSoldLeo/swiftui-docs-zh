--- 来源：https://developer.apple.com/documentation/SwiftUI/Button/init(_:action:)

抓取时间：2025-12-02T21:48:00Z

---

# init(_:action:)

**Initializer**

创建一个按钮，该按钮的标签由本地化的字符串键生成。

## 声明

```swift
@preconcurrency nonisolated init(_ titleKey: LocalizedStringKey, action: @escaping @MainActor () -> Void)
```

## 参数

- **titleKey**：按钮本地化标题的键，用于描述按钮的用途。`action`

- **action**：用户触发按钮时要执行的操作。

## 讨论

此初始化程序会代表您创建一个 [Text](../Text.zh-Hans.md) 视图，并以类似于 [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md) 的方式处理本地化键。有关字符串本地化的更多信息，请参阅 [Text](../Text.zh-Hans.md)。

## 创建按钮

- **init(action:label:)**：创建一个显示自定义标签的按钮。

- **init(_:image:action:)**：创建一个按钮，该按钮根据本地化字符串键和图像资源生成其标签。

- **init(_:systemImage:action:)**：创建一个按钮，该按钮根据本地化字符串键和系统图像名称生成其标签。


---
source: https://developer.apple.com/documentation/SwiftUI/Button/init(_:action:)
crawled: 2025-12-02T21:48:00Z
---

# init(_:action:)

**Initializer**

Creates a button that generates its label from a localized string key.

## Declaration

```swift
@preconcurrency nonisolated init(_ titleKey: LocalizedStringKey, action: @escaping @MainActor () -> Void)
```

## Parameters

- **titleKey**: The key for the button’s localized title, that describes the purpose of the button’s `action`.
- **action**: The action to perform when the user triggers the button.

## Discussion

This initializer creates a [Text](../Text.zh-Hans.md) view on your behalf, and treats the localized key similar to [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md). See [Text](../Text.zh-Hans.md) for more information about localizing strings.

## Creating a button

- **init(action:label:)**: Creates a button that displays a custom label.
- **init(_:image:action:)**: Creates a button that generates its label from a localized string key and image resource.
- **init(_:systemImage:action:)**: Creates a button that generates its label from a localized string key and system image name.

