---
来源：https://developer.apple.com/documentation/SwiftUI/Toggle/init(_:image:isOn:)
抓取时间： 2025-12-02T21:54:35Z
---

# init(_:image:isOn:)

**Initializer**

创建一个切换按钮，该按钮的标签由本地化字符串键和图像资源生成。

### 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, image: ImageResource, isOn: Binding<Bool>)
```

## 参数

- **titleKey**：切换按钮本地化标题的键值，描述切换按钮的目的。
- **image**：要查找的图像资源名称。
- **isOn**：与属性的绑定，表示切换是开还是关。

## 讨论

该初始化程序会代表您创建一个 [Text](../Text.zh-Hans.md) 视图，并处理与 [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md) 类似的本地化键。有关字符串本地化的更多信息，请参阅 `Text`。

## 创建切换

- **init(_:isOn:)**：创建一个通过本地化字符串键生成标签的切换按钮。
- **init(isOn:label:)**：创建显示自定义标签的切换按钮。
- **init(_:systemImage:isOn:)**：创建根据本地化字符串密钥和系统图像生成标签的切换按钮。


---
source: https://developer.apple.com/documentation/SwiftUI/Toggle/init(_:image:isOn:)
crawled: 2025-12-02T21:54:35Z
---

# init(_:image:isOn:)

**Initializer**

Creates a toggle that generates its label from a localized string key and image resource.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, image: ImageResource, isOn: Binding<Bool>)
```

## Parameters

- **titleKey**: The key for the toggle’s localized title, that describes the purpose of the toggle.
- **image**: The name of the image resource to lookup.
- **isOn**: A binding to a property that indicates whether the toggle is on or off.

## Discussion

This initializer creates a [Text](../Text.zh-Hans.md) view on your behalf, and treats the localized key similar to [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md). See `Text` for more information about localizing strings.

## Creating a toggle

- **init(_:isOn:)**: Creates a toggle that generates its label from a localized string key.
- **init(isOn:label:)**: Creates a toggle that displays a custom label.
- **init(_:systemImage:isOn:)**: Creates a toggle that generates its label from a localized string key and system image.

