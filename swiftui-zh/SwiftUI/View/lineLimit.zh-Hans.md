--- 来源：https://developer.apple.com/documentation/SwiftUI/View/lineLimit(_:)

抓取时间：2025-12-02T17:35:08Z

---

# lineLimit(_:)

**实例方法**

设置此视图中文本可占据的行数范围。

## 声明

```swift
nonisolated func lineLimit(_ limit: ClosedRange<Int>) -> some View

```

## 参数

- **limit**：行数限制。

## 说明

使用此修饰符可指定视图或垂直视图可占据的行数范围。[Text](../Text.zh-Hans.md) 或 [TextField](../TextField.zh-Hans.md)当此类视图中的文本占用空间超过设定的限制时，[Text](../Text.zh-Hans.md) 视图会截断其内容，而 [TextField](../TextField.zh-Hans.md) 视图则会变为可滚动视图。

```swift
Form {
    TextField("Title", text: $model.title)
    TextField("Notes", text: $model.notes, axis: .vertical)
        .lineLimit(1...3)
}
```

## 限制多行文本的行数

- **lineLimit(_:reservesSpace:)**：设置此视图中文本可占用的行数上限。

- **lineLimit**：视图中文本可占用的最大行数。


---
source: https://developer.apple.com/documentation/SwiftUI/View/lineLimit(_:)
crawled: 2025-12-02T17:35:08Z
---

# lineLimit(_:)

**Instance Method**

Sets to a closed range the number of lines that text can occupy in this view.

## Declaration

```swift
nonisolated func lineLimit(_ limit: ClosedRange<Int>) -> some View

```

## Parameters

- **limit**: The line limit.

## Discussion

Use this modifier to specify a closed range of lines that a [Text](../Text.zh-Hans.md) view or a vertical [TextField](../TextField.zh-Hans.md) can occupy. When the text of such views occupies more space than the provided limit, a [Text](../Text.zh-Hans.md) view truncates its content while a [TextField](../TextField.zh-Hans.md) becomes scrollable.

```swift
Form {
    TextField("Title", text: $model.title)
    TextField("Notes", text: $model.notes, axis: .vertical)
        .lineLimit(1...3)
}
```

## Limiting line count for multiline text

- **lineLimit(_:reservesSpace:)**: Sets a limit for the number of lines text can occupy in this view.
- **lineLimit**: The maximum number of lines that text can occupy in a view.

