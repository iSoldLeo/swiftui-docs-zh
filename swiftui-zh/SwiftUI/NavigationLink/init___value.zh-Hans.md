---
来源：https://developer.apple.com/documentation/SwiftUI/NavigationLink/init(_:value:)
抓取时间：2025-12-02T20:58:44Z
---

# init(_:value:)

**Initializer**

创建导航链接，显示与可编码值相对应的视图，并带有由本地化字符串键生成的文本标签。

### 声明

```swift
nonisolated init<P>(_ titleKey: LocalizedStringKey, value: P?) where Label == Text, P : Decodable, P : Encodable, P : Hashable
```

## 参数

- **titleKey**：描述此链接显示的视图的本地化字符串。
- **value**：要显示的可选值。当有人点击或单击链接时，SwiftUI 会存储该值的副本。传递`nil` 值可禁用该链接。

## 讨论

当有人激活此初始化程序创建的导航链接时，SwiftUI 会查找附近的[navigationDestination(for:destination:)](../View/navigationDestination_for_destination.zh-Hans.md) 视图修改器，该视图修改器具有与此初始化程序的`data` 输入参数类型相匹配的`value` 输入参数，结果如下：

- 如果 SwiftUI 在外层[NavigationStack](../NavigationStack.zh-Hans.md) 的视图层次结构中找到匹配的修改器，则会将该修改器对应的`destination` 视图推入堆栈。
- 如果 SwiftUI 在[NavigationSplitView](../NavigationSplitView.zh-Hans.md) 的后一列堆栈视图层次结构中找到了匹配的修改器，则会将修改器的目标视图作为第一个也是唯一一个项目放入堆栈，同时保留堆栈的根视图。
- 如果没有匹配的修改器，但链接出现在导航拆分视图的前导列内有选择的[List](../List.zh-Hans.md)中，则链接会更新选择，这可能会影响尾部视图的外观。有关示例，请参阅 [NavigationLink](../NavigationLink.zh-Hans.md)。
- 在其他情况下，链接不起任何作用。

由于该初始化器的值符合[doc://com.apple.documentation/documentation/Swift/Codable] 协议，因此可以确保包含该链接的[NavigationPath](../NavigationPath.zh-Hans.md) 可以为其 `nil` 属性生成一个非`nil` 值。这有助于使路径可序列化。

## 呈现一个值

- **init(value:label:)**：创建一个导航链接，显示与可编码值相对应的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationLink/init(_:value:)
crawled: 2025-12-02T20:58:44Z
---

# init(_:value:)

**Initializer**

Creates a navigation link that presents the view corresponding to a codable value, with a text label that the link generates from a localized string key.

## Declaration

```swift
nonisolated init<P>(_ titleKey: LocalizedStringKey, value: P?) where Label == Text, P : Decodable, P : Encodable, P : Hashable
```

## Parameters

- **titleKey**: A localized string that describes the view that this link presents.
- **value**: An optional value to present. When someone taps or clicks the link, SwiftUI stores a copy of the value. Pass a `nil` value to disable the link.

## Discussion

When someone activates the navigation link that this initializer creates, SwiftUI looks for a nearby [navigationDestination(for:destination:)](../View/navigationDestination_for_destination.zh-Hans.md) view modifier with a `data` input parameter that matches the type of this initializer’s `value` input, with one of the following outcomes:

- If SwiftUI finds a matching modifier within the view hierarchy of an enclosing [NavigationStack](../NavigationStack.zh-Hans.md), it pushes the modifier’s corresponding `destination` view onto the stack.
- If SwiftUI finds a matching modifier in the view hierarchy of a stack that’s in a later column of a [NavigationSplitView](../NavigationSplitView.zh-Hans.md), it puts the modifier’s destination view as the first and only item onto the stack while preserving the stack’s root view.
- If there’s no matching modifier, but the link appears in a [List](../List.zh-Hans.md) with selection inside a leading column of a navigation split view, the link updates the selection, which might affect the appearance of a trailing view. For an example of this, see [NavigationLink](../NavigationLink.zh-Hans.md).
- In other cases, the link doesn’t do anything.

Because this initializer takes a value that conforms to the [doc://com.apple.documentation/documentation/Swift/Codable] protocol, you ensure that a [NavigationPath](../NavigationPath.zh-Hans.md) that includes this link can produce a non-`nil` value for its [codable](../NavigationPath/codable.zh-Hans.md) property. This helps to make the path serializable.

## Presenting a value

- **init(value:label:)**: Creates a navigation link that presents the view corresponding to a codable value.

