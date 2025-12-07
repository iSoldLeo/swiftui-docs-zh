--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/Layout/DrawingOptions
抓取时间：2025-12-03T19:59:32Z

---

# Text.Layout.DrawingOptions

**Structure**

在图形上下文中绘制线条或运行时使用的选项标志。

## 声明

```swift
@frozen struct DrawingOptions
```

## 类型属性

- **disablesSubpixelQuantization**：如果设置，则禁用文本引擎请求的亚像素量化。这对于需要动画的文本非常有用，可以防止文本抖动。

## 符合以下标准

- 位可复制 (BitwiseCopyable)

- 可复制 (Copyable)

- 可等价 (Equatable)

- 数组字面量可表达 (ExpressibleByArrayLiteral)

- 选项集 (OptionSet)

- 原始表示 (RawRepresentable)

- 可发送 (Sendable)

- 可发送元类型 (SendableMetatype)

- 集合代数 (SetAlgebra)


---
source: https://developer.apple.com/documentation/SwiftUI/Text/Layout/DrawingOptions
crawled: 2025-12-03T19:59:32Z
---

# Text.Layout.DrawingOptions

**Structure**

Option flags used when drawing `Text.Layout` lines or runs into a graphics context.

## Declaration

```swift
@frozen struct DrawingOptions
```

## Type Properties

- **disablesSubpixelQuantization**: If set, subpixel quantization requested by the text engine is disabled. This can be useful for text that will be animated to prevent it jittering.

## Conforms To

- BitwiseCopyable
- Copyable
- Equatable
- ExpressibleByArrayLiteral
- OptionSet
- RawRepresentable
- Sendable
- SendableMetatype
- SetAlgebra

