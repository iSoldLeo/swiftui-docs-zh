--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/LineStyle/init(pattern:color:)

抓取时间：2025-12-02T00:44:21Z

---

# init(pattern:color:)

**Initializer**

创建线条样式。

## 声明

```swift
init(pattern: Text.LineStyle.Pattern = .solid, color: Color? = nil)
```

## 参数

- **pattern**：线条图案。

- **color**：线条颜色。如果未提供，则使用文本的前景色。

## 创建文本线条样式

- **init(nsUnderlineStyle:)**：根据 `NSUnderlineStyle` 创建 `Text.LineStyle`。

- **Text.LineStyle.Pattern**：该线条所呈现的图案。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/LineStyle/init(pattern:color:)
crawled: 2025-12-02T00:44:21Z
---

# init(pattern:color:)

**Initializer**

Creates a line style.

## Declaration

```swift
init(pattern: Text.LineStyle.Pattern = .solid, color: Color? = nil)
```

## Parameters

- **pattern**: The pattern of the line.
- **color**: The color of the line. If not provided, the foreground color of text is used.

## Creating a text line style

- **init(nsUnderlineStyle:)**: Creates a `Text.LineStyle` from `NSUnderlineStyle`.
- **Text.LineStyle.Pattern**: The pattern, that the line has.

