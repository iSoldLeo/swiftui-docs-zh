---
来源： https://developer.apple.com/documentation/SwiftUI/TextSelectability/disabled
抓取时间： 2025-12-03T06:17:30Z
---

# 禁用

**类型属性**

选择性值，用于禁止使用应用程序的用户选择文本。

## 声明

```swift
static var disabled: DisabledTextSelectability { get }
```

## 讨论

使用此属性可禁用不想让人选择和复制的视图的文本选择，即使这些视图包含在允许文本选择的整体上下文中。

```swift
content // Content that might contain Text views.
   .textSelection(.disabled)
   .padding()
   .contentShape(Rectangle())
   .gesture(someGesture)
```

## 获取可选择性选项

- **enabled**：可选性值，可让使用您应用程序的人选择文本。


---
source: https://developer.apple.com/documentation/SwiftUI/TextSelectability/disabled
crawled: 2025-12-03T06:17:30Z
---

# disabled

**Type Property**

A selectability value that disables text selection by the person using your app.

## Declaration

```swift
static var disabled: DisabledTextSelectability { get }
```

## Discussion

Use this property to disable text selection of views that you don’t want people to select and copy, even if contained within an overall context that allows text selection.

```swift
content // Content that might contain Text views.
   .textSelection(.disabled)
   .padding()
   .contentShape(Rectangle())
   .gesture(someGesture)
```

## Getting selectability options

- **enabled**: A selectability value that enables text selection by a person using your app.

