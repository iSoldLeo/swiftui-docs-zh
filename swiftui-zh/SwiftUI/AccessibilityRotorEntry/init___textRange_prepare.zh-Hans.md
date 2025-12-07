--- 来源：https://developer.apple.com/documentation/SwiftUI/AccessibilityRotorEntry/init(_:textRange:prepare:)

抓取时间：2025-12-01T11:39:22Z

---

# init(_:textRange:prepare:)

**Initializer**

创建一个具有特定标签和范围的 Rotor 条目。此 Rotor 条目将与拥有该 Rotor 的 Accessibility 元素关联。

## 声明

```swift
init(_ label: LocalizedStringResource, textRange: Range<String.Index>, prepare: @escaping () -> Void = {}) where ID == Never
```

## 参数

- **label**：用于向用户显示此 Rotor 条目的本地化字符串。如果未指定标签，则 Rotor 条目将根据该范围内的文本进行标记。

- **prepare**：在导航到 Rotor 条目之前运行的可选闭包，用于根据需要准备 UI。如果 UI 元素或文本尚未显示在屏幕上，且 SwiftUI 无法自动滚动到该元素或文本，则可以使用此闭包将其显示在屏幕上。

## 创建 Rotor 条目

- **init(_:id:textRange:prepare:)**：使用特定标签和标识符（可选范围）创建 Rotor 条目。


---
source: https://developer.apple.com/documentation/SwiftUI/AccessibilityRotorEntry/init(_:textRange:prepare:)
crawled: 2025-12-01T11:39:22Z
---

# init(_:textRange:prepare:)

**Initializer**

Create a Rotor entry with a specific label and range. This Rotor entry will be associated with the Accessibility element that owns the Rotor.

## Declaration

```swift
init(_ label: LocalizedStringResource, textRange: Range<String.Index>, prepare: @escaping () -> Void = {}) where ID == Never
```

## Parameters

- **label**: Localized string used to show this Rotor entry to users. If no label is specified, the Rotor entry will be labeled based on the text at that range.
- **prepare**: Optional closure to run before a Rotor entry is navigated to, to prepare the UI as needed. This can be used to bring the UI element or text on-screen if it isn’t already, and SwiftUI not able to automatically scroll to it.

## Creating a rotor entry

- **init(_:id:textRange:prepare:)**: Create a Rotor entry with a specific label and identifier, with an optional range.

