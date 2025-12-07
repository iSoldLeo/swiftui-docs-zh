---
来源： https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityValue(_:isEnabled:)
抓取时间： 2025-12-02T17:47:12Z
---

# accessibilityValue(_:isEnabled:)

**实例方法**

添加视图所含值的文字描述。

## 声明

```swift
nonisolated func accessibilityValue(_ valueDescription: Text, isEnabled: Bool) -> ModifiedContent<Content, Modifier>
```

## 参数

- **valueDescription**：要应用的可访问性值。
- **isEnabled**：如果为 true，则应用辅助功能值；否则辅助功能值保持不变。

## 讨论

使用此方法可以描述视图所代表的值，但前提是该值与视图的标签不同。例如，对于使用 accessibilityLabel() 标签为 "音量 "的滑块，可以使用 accessibilityValue() 提供当前音量设置，如 "60%"。


---
source: https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityValue(_:isEnabled:)
crawled: 2025-12-02T17:47:12Z
---

# accessibilityValue(_:isEnabled:)

**Instance Method**

Adds a textual description of the value that the view contains.

## Declaration

```swift
nonisolated func accessibilityValue(_ valueDescription: Text, isEnabled: Bool) -> ModifiedContent<Content, Modifier>
```

## Parameters

- **valueDescription**: The accessibility value to apply.
- **isEnabled**: If true the accessibility value is applied; otherwise the accessibility value is unchanged.

## Discussion

Use this method to describe the value represented by a view, but only if that’s different than the view’s label. For example, for a slider that you label as “Volume” using accessibilityLabel(), you can provide the current volume setting, like “60%”, using accessibilityValue().

