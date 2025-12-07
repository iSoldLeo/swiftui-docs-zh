---
来源： https://developer.apple.com/documentation/SwiftUI/ResetFocusAction/callAsFunction(in:)
抓取时间： 2025-12-01T11:37:14Z
---

# callAsFunction(in:)

**实例方法**

要求焦点系统重新评估默认焦点项。

## 声明

```swift
func callAsFunction(in namespace: Namespace.ID)
```

## 参数

- **namespace**：SwiftUI 应重新评估默认焦点的命名空间。该命名空间应与需要重新评估焦点的 [focusScope(_:)](../View/focusScope.zh-Hans.md) 块相匹配。

## 讨论

当当前关注的项目位于所提供的命名空间内时，焦点系统会重新评估默认焦点。


---
source: https://developer.apple.com/documentation/SwiftUI/ResetFocusAction/callAsFunction(in:)
crawled: 2025-12-01T11:37:14Z
---

# callAsFunction(in:)

**Instance Method**

Asks the focus sytem to reevaluate the default focus item.

## Declaration

```swift
func callAsFunction(in namespace: Namespace.ID)
```

## Parameters

- **namespace**: The namespace inside which SwiftUI should reevaluate default focus. The namespace should match the [focusScope(_:)](../View/focusScope.zh-Hans.md) block where focus requires reevaluation.

## Discussion

The focus system reevaluates default focus when the currently-focused item is within the provided namespace.

