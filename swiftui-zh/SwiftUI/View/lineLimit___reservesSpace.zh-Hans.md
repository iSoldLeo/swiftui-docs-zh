--- 来源：https://developer.apple.com/documentation/SwiftUI/View/lineLimit(_:reservesSpace:)

抓取时间：2025-12-02T17:35:09Z

---

# lineLimit(_:reservesSpace:)

**实例方法**

设置此视图中文本可占据的行数限制。

## 声明

```swift
nonisolated func lineLimit(_ limit: Int, reservesSpace: Bool) -> some View

```

## 参数

- **limit**：行数限制。

- **reservesSpace**：文本是否预留空间，使其始终占据显示指定行数所需的高度。

## 说明

使用此修饰符可指定 [Text](../Text.zh-Hans.md) 或垂直 [TextField](../TextField.zh-Hans.md) 可占据的行数限制。如果将 `reservesSpace` 参数的值设置为 true，且此类视图的文本占用空间小于设定的限制，则该视图将扩展以占用最少的行数。当文本占用空间大于设定的限制时，[Text](../Text.zh-Hans.md) 视图的内容将被截断，而 [TextField](../TextField.zh-Hans.md) 视图将变为可滚动视图。

```swift
GroupBox {
    Text("Title")
        .font(.headline)
        .lineLimit(2, reservesSpace: true)
    Text("Subtitle")
        .font(.subheadline)
        .lineLimit(4, reservesSpace: true)
}
```

## 限制多行文本的行数

- **lineLimit(_:)**：设置此视图中文本可占用的行数范围。

- **lineLimit**：视图中文本可占用的最大行数。


---
source: https://developer.apple.com/documentation/SwiftUI/View/lineLimit(_:reservesSpace:)
crawled: 2025-12-02T17:35:09Z
---

# lineLimit(_:reservesSpace:)

**Instance Method**

Sets a limit for the number of lines text can occupy in this view.

## Declaration

```swift
nonisolated func lineLimit(_ limit: Int, reservesSpace: Bool) -> some View

```

## Parameters

- **limit**: The line limit.
- **reservesSpace**: Whether text reserves space so that it always occupies the height required to display the specified number of lines.

## Discussion

Use this modifier to specify a limit to the lines that a [Text](../Text.zh-Hans.md) or a vertical [TextField](../TextField.zh-Hans.md) may occupy. If passed a value of true for the `reservesSpace` parameter, and the text of such views occupies less space than the provided limit, that view expands to occupy the minimum number of lines. When the text occupies more space than the provided limit, a [Text](../Text.zh-Hans.md) view truncates its content while a [TextField](../TextField.zh-Hans.md) becomes scrollable.

```swift
GroupBox {
    Text("Title")
        .font(.headline)
        .lineLimit(2, reservesSpace: true)
    Text("Subtitle")
        .font(.subheadline)
        .lineLimit(4, reservesSpace: true)
}
```

## Limiting line count for multiline text

- **lineLimit(_:)**: Sets to a closed range the number of lines that text can occupy in this view.
- **lineLimit**: The maximum number of lines that text can occupy in a view.

