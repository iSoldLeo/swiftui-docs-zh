--- 来源：https://developer.apple.com/documentation/SwiftUI/Button/init(_:intent:)

抓取时间：2025-12-01T02:38:58Z

---

# init(_:intent:)

**Initializer**

创建一个按钮，该按钮执行 `AppIntent` 操作，并根据本地化字符串键生成其标签。

## 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, intent: some AppIntent)
```

## 参数

- **titleKey**：按钮本地化标题的键，用于描述按钮 `intent` 的用途。

- **intent**：要执行的 `AppIntent` 操作。

## 讨论

此初始化程序会代表您创建一个 [Text](../Text.zh-Hans.md) 视图，并以类似于 [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md) 的方式处理本地化键。有关字符串本地化的更多信息，请参阅 [Text](../Text.zh-Hans.md)。

要使用字符串变量初始化按钮，请改用 [init(_:intent:)](init___intent.zh-Hans.md)。

## 创建按钮以执行 App Intent

- **init(intent:label:)**：创建一个执行 `AppIntent` 的按钮。

- **init(_:role:intent:)**：创建一个具有指定角色的按钮，该按钮执行 `AppIntent` 并从字符串生成其标签。

- **init(role:intent:label:)**：创建一个具有指定角色的按钮，该按钮执行 `AppIntent`。

- **init(_:image:role:intent:)**：创建一个具有指定角色的按钮，该按钮的标签由字符串和图像资源生成。

- **init(_:systemImage:role:intent:)**：创建一个具有指定角色的按钮，该按钮的标签由字符串和系统图像生成。


---
source: https://developer.apple.com/documentation/SwiftUI/Button/init(_:intent:)
crawled: 2025-12-01T02:38:58Z
---

# init(_:intent:)

**Initializer**

Creates a button that performs an `AppIntent` and generates its label from a localized string key.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, intent: some AppIntent)
```

## Parameters

- **titleKey**: The key for the button’s localized title, that describes the purpose of the button’s `intent`.
- **intent**: The `AppIntent` to execute.

## Discussion

This initializer creates a [Text](../Text.zh-Hans.md) view on your behalf, and treats the localized key similar to [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md). See [Text](../Text.zh-Hans.md) for more information about localizing strings.

To initialize a button with a string variable, use [init(_:intent:)](init___intent.zh-Hans.md) instead.

## Creating a button to perform an App Intent

- **init(intent:label:)**: Creates a button that performs an `AppIntent`.
- **init(_:role:intent:)**: Creates a button with a specified role that performs an `AppIntent` and generates its label from a string.
- **init(role:intent:label:)**: Creates a button with a specified role that performs an `AppIntent`.
- **init(_:image:role:intent:)**: Creates a button with a specified role that generates its label from a string and an image resource.
- **init(_:systemImage:role:intent:)**: Creates a button with a specified role that generates its label from a string and a system image.

