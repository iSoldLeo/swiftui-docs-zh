--- 来源：https://developer.apple.com/documentation/SwiftUI/ProposedViewSize/replacingUnspecifiedDimensions(by:)

抓取时间：2025-12-03T06:39:31Z

---

# replacementUnspecifiedDimensions(by:)

**实例方法**

创建一个新的建议，将当前建议中未指定的尺寸替换为指定尺寸的对应尺寸。

## 声明

```swift
func replacingUnspecifiedDimensions(by size: CGSize = CGSize(width: 10, height: 10)) -> CGSize
```

## 参数

- **size**：一组用于尺寸建议的具体值，以替换任何未指定的尺寸。默认值为 `10`，两个尺寸均如此。

## 返回值

一个新的、完全指定的尺寸建议。

## 讨论

使用默认值可防止灵活视图消失于零尺寸框架中，并确保未指定的值在调试期间保持可见。


---
source: https://developer.apple.com/documentation/SwiftUI/ProposedViewSize/replacingUnspecifiedDimensions(by:)
crawled: 2025-12-03T06:39:31Z
---

# replacingUnspecifiedDimensions(by:)

**Instance Method**

Creates a new proposal that replaces unspecified dimensions in this proposal with the corresponding dimension of the specified size.

## Declaration

```swift
func replacingUnspecifiedDimensions(by size: CGSize = CGSize(width: 10, height: 10)) -> CGSize
```

## Parameters

- **size**: A set of concrete values to use for the size proposal in place of any unspecified dimensions. The default value is `10` for both dimensions.

## Return Value

A new, fully specified size proposal.

## Discussion

Use the default value to prevent a flexible view from disappearing into a zero-sized frame, and ensure the unspecified value remains visible during debugging.

