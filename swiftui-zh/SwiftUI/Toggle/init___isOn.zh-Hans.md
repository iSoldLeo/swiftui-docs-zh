---
来源：https://developer.apple.com/documentation/SwiftUI/Toggle/init(_:isOn:)
抓取时间： 2025-12-02T21:54:33Z
---

# init(_:isOn:)

**Initializer**

创建一个切换器，通过本地化的字符串键生成标签。

## 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, isOn: Binding<Bool>)
```

## 参数

- **titleKey**：切换按钮本地化标题的键值，描述切换按钮的用途。
- **isOn**：与属性的绑定，用于指示切换是打开还是关闭。

## 讨论

该初始化程序会代表您创建一个 [Text](../Text.zh-Hans.md) 视图，并处理与 [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md) 类似的本地化键。有关字符串本地化的更多信息，请参阅 `Text`。

## 创建切换

- **init(isOn:label:)**：创建显示自定义标签的切换按钮。
- **init(_:image:isOn:)**：创建根据本地化字符串键和图像资源生成标签的切换按钮。
- **init(_:systemImage:isOn:)**：创建根据本地化字符串键和系统图像生成标签的切换按钮。


---
source: https://developer.apple.com/documentation/SwiftUI/Toggle/init(_:isOn:)
crawled: 2025-12-02T21:54:33Z
---

# init(_:isOn:)

**Initializer**

Creates a toggle that generates its label from a localized string key.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, isOn: Binding<Bool>)
```

## Parameters

- **titleKey**: The key for the toggle’s localized title, that describes the purpose of the toggle.
- **isOn**: A binding to a property that indicates whether the toggle is on or off.

## Discussion

This initializer creates a [Text](../Text.zh-Hans.md) view on your behalf, and treats the localized key similar to [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md). See `Text` for more information about localizing strings.

## Creating a toggle

- **init(isOn:label:)**: Creates a toggle that displays a custom label.
- **init(_:image:isOn:)**: Creates a toggle that generates its label from a localized string key and image resource.
- **init(_:systemImage:isOn:)**: Creates a toggle that generates its label from a localized string key and system image.

