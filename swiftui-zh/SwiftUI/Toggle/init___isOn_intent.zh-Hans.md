---
来源：https://developer.apple.com/documentation/SwiftUI/Toggle/init(_:isOn:intent:)
抓取时间： 2025-12-01T02:45:34Z
---

# init(_:isOn:intent:)

**Initializer**

创建一个执行`AppIntent` 的切换器，并通过本地化的字符串键生成其标签。

### 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, isOn: Bool, intent: some AppIntent)
```

## 参数

- **titleKey**：切换按钮本地化标题的键值，描述切换按钮的目的。
- **isOn**：切换是打开还是关闭。
- **intent**：要执行的`AppIntent`。

## 讨论

该初始化程序会代表您创建一个 [Text](../Text.zh-Hans.md) 视图，并处理与 [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md) 类似的本地化键。有关字符串本地化的更多信息，请参见 `Text`。

要使用字符串变量初始化切换开关，请使用 [init(_:isOn:intent:)](init___isOn_intent.zh-Hans.md)。

## 为应用程序意图创建切换按钮

- **init(isOn:intent:label:)**：创建执行`AppIntent`的切换。


---
source: https://developer.apple.com/documentation/SwiftUI/Toggle/init(_:isOn:intent:)
crawled: 2025-12-01T02:45:34Z
---

# init(_:isOn:intent:)

**Initializer**

Creates a toggle performing an `AppIntent` and generates its label from a localized string key.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, isOn: Bool, intent: some AppIntent)
```

## Parameters

- **titleKey**: The key for the toggle’s localized title, that describes the purpose of the toggle.
- **isOn**: Whether the toggle is on or off.
- **intent**: The `AppIntent` to be performed.

## Discussion

This initializer creates a [Text](../Text.zh-Hans.md) view on your behalf, and treats the localized key similar to [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md). See `Text` for more information about localizing strings.

To initialize a toggle with a string variable, use [init(_:isOn:intent:)](init___isOn_intent.zh-Hans.md) instead.

## Creating a toggle for an App Intent

- **init(isOn:intent:label:)**: Creates a toggle performing an `AppIntent`.

