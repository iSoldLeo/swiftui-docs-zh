--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/AlignmentStrategy/writingDirectionBased

抓取时间：2025-12-03T19:59:30Z

---

# writingDirectionBased

**类型属性**

段落的对齐方式，即文本是否跟随书写方向。

## 声明

```swift
static let writingDirectionBased: Text.AlignmentStrategy
```

## 说明

当 [multilineTextAlignment](../../EnvironmentValues/multilineTextAlignment.zh-Hans.md) 为 [leading](../../TextAlignment/leading.zh-Hans.md) 时，文本对齐方式与书写方向一致。如果值为 [trailing](../../TextAlignment/trailing.zh-Hans.md)，则文本对齐方式与书写方向相反。最后，[center](../../TextAlignment/center.zh-Hans.md) 的值始终导致文本居中对齐。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/AlignmentStrategy/writingDirectionBased
crawled: 2025-12-03T19:59:30Z
---

# writingDirectionBased

**Type Property**

The alignment following the writing direction of the same paragraph.

## Declaration

```swift
static let writingDirectionBased: Text.AlignmentStrategy
```

## Discussion

When [multilineTextAlignment](../../EnvironmentValues/multilineTextAlignment.zh-Hans.md) is [leading](../../TextAlignment/leading.zh-Hans.md), alignment follows the writing direction. If the value is [trailing](../../TextAlignment/trailing.zh-Hans.md) alignment is the opposite of the writing direction and finally, a [center](../../TextAlignment/center.zh-Hans.md) value always results in centered alignment.

