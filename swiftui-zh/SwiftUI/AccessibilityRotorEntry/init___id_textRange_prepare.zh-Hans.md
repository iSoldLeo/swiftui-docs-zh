--- 来源：https://developer.apple.com/documentation/SwiftUI/AccessibilityRotorEntry/init(_:id:textRange:prepare:)

抓取时间：2025-12-01T11:39:23Z

---

# init(_:id:textRange:prepare:)

**Initializer**

创建一个具有特定标签和标识符的 Rotor 条目，并可选择指定范围。

## 声明

```swift
init(_ label: LocalizedStringResource, id: ID, textRange: Range<String.Index>? = nil, prepare: @escaping () -> Void = {})
```

## 参数

- **label**：用于向用户显示此 Rotor 条目的本地化字符串。

- **id**：用于查找与此 Rotor 条目关联的 UI 元素。此标识符应在 `scrollView` 中使用，可以是在 `ForEach` 中，也可以通过 `id` 调用。

- **textRange**：与此 Rotor 条目关联的可选文本范围。此范围应位于设置为关联元素的辅助功能标签或辅助功能值的文本范围内。

- **prepare**：在导航到 Rotor 条目之前运行的可选闭包，用于根据需要准备 UI。如果 UI 元素尚未显示在屏幕上，且 SwiftUI 无法自动滚动到该元素，则可以使用此闭包将其显示在屏幕上。

## 创建 Rotor 条目

- **init(_:textRange:prepare:)**：创建具有特定标签和范围的 Rotor 条目。此 Rotor 条目将与拥有该 Rotor 的辅助功能元素关联。


---
source: https://developer.apple.com/documentation/SwiftUI/AccessibilityRotorEntry/init(_:id:textRange:prepare:)
crawled: 2025-12-01T11:39:23Z
---

# init(_:id:textRange:prepare:)

**Initializer**

Create a Rotor entry with a specific label and identifier, with an optional range.

## Declaration

```swift
init(_ label: LocalizedStringResource, id: ID, textRange: Range<String.Index>? = nil, prepare: @escaping () -> Void = {})
```

## Parameters

- **label**: Localized string used to show this Rotor entry to users.
- **id**: Used to find the UI element associated with this Rotor entry. This identifier should be used within a `scrollView`, either in a `ForEach` or using an `id` call.
- **textRange**: Optional range of text associated with this Rotor entry. This should be a range within text that is set as the accessibility label or accessibility value of the associated element.
- **prepare**: Optional closure to run before a Rotor entry is navigated to, to prepare the UI as needed. This can be used to bring the UI element on-screen if it isn’t already, and SwiftUI is not able to automatically scroll to it.

## Creating a rotor entry

- **init(_:textRange:prepare:)**: Create a Rotor entry with a specific label and range. This Rotor entry will be associated with the Accessibility element that owns the Rotor.

