---
来源： https://developer.apple.com/documentation/SwiftUI/Toggle/init(_:image:sources:isOn:)
抓取时间：2025-12-01T02:45:31Z
---

# init(_:image:sources:isOn:)

**Initializer**

创建代表值集合的切换按钮，该按钮的标签由本地化字符串键和图像资源生成。

### 声明

```swift
nonisolated init<C>(_ titleKey: LocalizedStringKey, image: ImageResource, sources: C, isOn: KeyPath<C.Element, Binding<Bool>>) where C : RandomAccessCollection
```

## 参数

- **titleKey**：切换按钮本地化标题的键值，描述切换按钮的目的。
- **image**：要查找的图像资源名称。
- **sources**：用作渲染 Toggle 状态源的值集合。
- **isOn**：决定切换是打开、混合还是关闭的值的关键路径。

## 讨论

该初始化程序会代表您创建一个 [Text](../Text.zh-Hans.md) 视图，并处理与 [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md) 类似的本地化键值。有关字符串本地化的更多信息，请参见 `Text`。

下面的示例创建了一个表示多个警报状态的单个切换器：

```swift
struct Alarm: Hashable, Identifiable {
    var id = UUID()
    var isOn = false
    var name = ""
}

@State private var alarms = [
    Alarm(isOn: true, name: "Morning"),
    Alarm(isOn: false, name: "Evening")
]

Toggle("Enable all alarms", sources: $alarms, isOn: \.isOn)
```

## 为警报集合创建一个切换器

- **init(_:sources:isOn:)**：创建一个代表值集合的切换按钮，其标签由本地化字符串键生成。
- **init(sources:isOn:label:)**：创建一个带有自定义标签的切换按钮，代表一个值集合。
- **init(_:systemImage:sources:isOn:)**：创建代表值集合的切换按钮，该按钮的标签由本地化字符串密钥和系统图像生成。


---
source: https://developer.apple.com/documentation/SwiftUI/Toggle/init(_:image:sources:isOn:)
crawled: 2025-12-01T02:45:31Z
---

# init(_:image:sources:isOn:)

**Initializer**

Creates a toggle representing a collection of values that generates its label from a localized string key and image resource.

## Declaration

```swift
nonisolated init<C>(_ titleKey: LocalizedStringKey, image: ImageResource, sources: C, isOn: KeyPath<C.Element, Binding<Bool>>) where C : RandomAccessCollection
```

## Parameters

- **titleKey**: The key for the toggle’s localized title, that describes the purpose of the toggle.
- **image**: The name of the image resource to lookup.
- **sources**: A collection of values used as the source for rendering the Toggle’s state.
- **isOn**: The key path of the values that determines whether the toggle is on, mixed or off.

## Discussion

This initializer creates a [Text](../Text.zh-Hans.md) view on your behalf, and treats the localized key similar to [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md). See `Text` for more information about localizing strings.

The following example creates a single toggle that represents the state of multiple alarms:

```swift
struct Alarm: Hashable, Identifiable {
    var id = UUID()
    var isOn = false
    var name = ""
}

@State private var alarms = [
    Alarm(isOn: true, name: "Morning"),
    Alarm(isOn: false, name: "Evening")
]

Toggle("Enable all alarms", sources: $alarms, isOn: \.isOn)
```

## Creating a toggle for a collection

- **init(_:sources:isOn:)**: Creates a toggle representing a collection of values that generates its label from a localized string key.
- **init(sources:isOn:label:)**: Creates a toggle representing a collection of values with a custom label.
- **init(_:systemImage:sources:isOn:)**: Creates a toggle representing a collection of values that generates its label from a localized string key and system image.

