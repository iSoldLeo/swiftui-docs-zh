--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/LineStyle/init(nsUnderlineStyle:)

抓取时间：2025-12-02T00:44:20Z

---

# init(nsUnderlineStyle:)

**Initializer**

从 `NSUnderlineStyle` 创建一个 `Text.LineStyle`。

## 声明

```swift
init?(nsUnderlineStyle: NSUnderlineStyle)
```

## 参数

- **nsUnderlineStyle**：一个 `NSUnderlineStyle` 的值，用于包裹 `Text.LineStyle`。

## 返回值

当 `nsUnderlineStyle` 包含 `Text.LineStyle` 不支持的样式时，返回一个新的 `Text.LineStyle` 或 `nil`。

## 讨论

## 创建文本行样式

- **init(pattern:color:)**：创建行样式。

- **Text.LineStyle.Pattern**：行样式所用的图案。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/LineStyle/init(nsUnderlineStyle:)
crawled: 2025-12-02T00:44:20Z
---

# init(nsUnderlineStyle:)

**Initializer**

Creates a `Text.LineStyle` from `NSUnderlineStyle`.

## Declaration

```swift
init?(nsUnderlineStyle: NSUnderlineStyle)
```

## Parameters

- **nsUnderlineStyle**: A value of `NSUnderlineStyle` to wrap with `Text.LineStyle`.

## Return Value

A new `Text.LineStyle` or `nil` when `nsUnderlineStyle` contains styles not supported by `Text.LineStyle`.

## Discussion



## Creating a text line style

- **init(pattern:color:)**: Creates a line style.
- **Text.LineStyle.Pattern**: The pattern, that the line has.

