--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/LineStyle/Pattern
抓取时间：2025-12-03T19:59:25Z

---

# Text.LineStyle.Pattern

**Structure**

线条的图案。

## 声明

```swift
struct Pattern
```

## 获取线条样式图案

- **solid**：绘制实线。

- **dot**：绘制点线。

- **dash**：绘制虚线。

- **dashDot**

- **dashDotDot**：绘制虚线和点线交替的线条。

## 创建文本行样式

- **init(nsUnderlineStyle:)**：从 `NSUnderlineStyle` 创建 `Text.LineStyle`。

- **init(pattern:color:)**：创建行样式。

## 符合以下规范

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/Text/LineStyle/Pattern
crawled: 2025-12-03T19:59:25Z
---

# Text.LineStyle.Pattern

**Structure**

The pattern, that the line has.

## Declaration

```swift
struct Pattern
```

## Getting line style patterns

- **solid**: Draw a solid line.
- **dot**: Draw a line of dots.
- **dash**: Draw a line of dashes.
- **dashDot**
- **dashDotDot**: Draw a line of alternating dashes and two dots.

## Creating a text line style

- **init(nsUnderlineStyle:)**: Creates a `Text.LineStyle` from `NSUnderlineStyle`.
- **init(pattern:color:)**: Creates a line style.

## Conforms To

- Sendable
- SendableMetatype

