---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/lineLimit
抓取时间： 2025-12-02T17:35:10Z
---

# lineLimit

**实例属性**

视图中文本可占用的最大行数。

## 声明

```swift
var lineLimit: Int? { get set }
```

## 讨论

如果`1`的值小于`1`，则最大行数为`1`。如果值为 `nil`，文本将使用所需的行数。默认值为 `nil`。

## 限制多行文本的行数

- **lineLimit(_:)**：将此视图中文本可占用的行数设置为封闭范围。
- **lineLimit(_:reservesSpace:)**：设置此视图中文本可占用的行数限制。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/lineLimit
crawled: 2025-12-02T17:35:10Z
---

# lineLimit

**Instance Property**

The maximum number of lines that text can occupy in a view.

## Declaration

```swift
var lineLimit: Int? { get set }
```

## Discussion

The maximum number of lines is `1` if the value is less than `1`. If the value is `nil`, the text uses as many lines as required. The default is `nil`.

## Limiting line count for multiline text

- **lineLimit(_:)**: Sets to a closed range the number of lines that text can occupy in this view.
- **lineLimit(_:reservesSpace:)**: Sets a limit for the number of lines text can occupy in this view.

