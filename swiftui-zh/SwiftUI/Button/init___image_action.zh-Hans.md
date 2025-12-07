--- 来源：https://developer.apple.com/documentation/SwiftUI/Button/init(_:image:action:)

抓取时间：2025-12-01T02:38:52Z

---

# init(_:image:action:)

**Initializer**

创建一个按钮，该按钮的标签由本地化的字符串键和图像资源生成。

## 声明

```swift
@preconcurrency nonisolated init(_ titleKey: LocalizedStringKey, image: ImageResource, action: @escaping @MainActor () -> Void)
```

## 参数

- **titleKey**：按钮本地化标题的键，用于描述按钮的用途。`action`

- **image**：要查找的图像资源。

- **action**：用户触发按钮时要执行的操作。

## 讨论

此初始化程序会代表您创建一个 [Label](../Label.zh-Hans.md) 视图，并以类似于 [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md) 的方式处理本地化键。有关字符串本地化的更多信息，请参阅 [Text](../Text.zh-Hans.md)。

## 创建按钮

- **init(action:label:)**：创建一个显示自定义标签的按钮。

- **init(_:action:)**：创建一个根据本地化字符串键生成标签的按钮。

- **init(_:systemImage:action:)**：创建一个根据本地化字符串键和系统映像名称生成标签的按钮。


---
source: https://developer.apple.com/documentation/SwiftUI/Button/init(_:image:action:)
crawled: 2025-12-01T02:38:52Z
---

# init(_:image:action:)

**Initializer**

Creates a button that generates its label from a localized string key and image resource.

## Declaration

```swift
@preconcurrency nonisolated init(_ titleKey: LocalizedStringKey, image: ImageResource, action: @escaping @MainActor () -> Void)
```

## Parameters

- **titleKey**: The key for the button’s localized title, that describes the purpose of the button’s `action`.
- **image**: The image resource to lookup.
- **action**: The action to perform when the user triggers the button.

## Discussion

This initializer creates a [Label](../Label.zh-Hans.md) view on your behalf, and treats the localized key similar to [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md). See [Text](../Text.zh-Hans.md) for more information about localizing strings.

## Creating a button

- **init(action:label:)**: Creates a button that displays a custom label.
- **init(_:action:)**: Creates a button that generates its label from a localized string key.
- **init(_:systemImage:action:)**: Creates a button that generates its label from a localized string key and system image name.

