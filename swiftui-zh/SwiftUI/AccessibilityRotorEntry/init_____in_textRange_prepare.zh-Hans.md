--- 来源：https://developer.apple.com/documentation/SwiftUI/AccessibilityRotorEntry/init(_:_:in:textRange:prepare:)

抓取时间：2025-12-03T06:50:14Z

---

# init(_:_:in:textRange:prepare:)

**Initializer**

创建一个具有特定标签、标识符和命名空间的 Rotor 条目，并可选择性地指定范围。

## 声明

```swift
init<L>(_ label: L, _ id: ID, in namespace: Namespace.ID, textRange: Range<String.Index>? = nil, prepare: @escaping () -> Void = {}) where L : StringProtocol
```

## 参数

- **label**：用于向用户显示此 Rotor 条目的本地化字符串。

- **id**：用于查找与此 Rotor 条目关联的 UI 元素。此标识符和命名空间应与对 `accessibilityRotorEntry(id:in)` 的调用匹配。

- **namespace**：此标识符的命名空间。应与对 `accessibilityRotorEntry(id:in)` 的调用匹配。

- **textRange**：与此 Rotor 条目关联的可选文本范围。此范围应位于设置为关联元素的辅助功能标签或辅助功能值的文本范围内。

- **prepare**：在导航到 Rotor 条目之前运行的可选闭包，用于根据需要准备 UI。如果需要滚动才能访问辅助功能元素，则应使用此闭包将其显示在屏幕上。

## 在命名空间中创建已标识的 Rotor 条目

- **init(_:id:in:textRange:prepare:)**：创建具有特定标签、标识符和命名空间以及可选范围的 Rotor 条目。


---
source: https://developer.apple.com/documentation/SwiftUI/AccessibilityRotorEntry/init(_:_:in:textRange:prepare:)
crawled: 2025-12-03T06:50:14Z
---

# init(_:_:in:textRange:prepare:)

**Initializer**

Create a Rotor entry with a specific label, identifier and namespace, and with an optional range.

## Declaration

```swift
init<L>(_ label: L, _ id: ID, in namespace: Namespace.ID, textRange: Range<String.Index>? = nil, prepare: @escaping () -> Void = {}) where L : StringProtocol
```

## Parameters

- **label**: Localized string used to show this Rotor entry to users.
- **id**: Used to find the UI element associated with this Rotor entry. This identifier and namespace should match a call to `accessibilityRotorEntry(id:in)`.
- **namespace**: Namespace for this identifier. Should match a call to `accessibilityRotorEntry(id:in)`.
- **textRange**: Optional range of text associated with this Rotor entry. This should be a range within text that is set as the accessibility label or accessibility value of the associated element.
- **prepare**: Optional closure to run before a Rotor entry is navigated to, to prepare the UI as needed. This should be used to bring the Accessibility element on-screen, if scrolling is needed to get to it.

## Creating an identified rotor entry in a namespace

- **init(_:id:in:textRange:prepare:)**: Create a Rotor entry with a specific label, identifier and namespace, and with an optional range.

