---
来源： https://developer.apple.com/documentation/SwiftUI/AttributedTextSelection/attributes(in:)
抓取时间： 2025-12-03T06:17:45Z
---

# attributes(in:)

**实例方法**

获取给定文本中选中的所有属性值的懒序列。

## 声明

```swift
func attributes(in text: AttributedString) -> AttributedTextSelection.Attributes<AttributedString>
```

## 讨论

选区的属性值是完全选中或部分选中的每个运行的属性值，如果选区是插入点，则是键入属性。

默认情况下，序列包含每个运行的属性容器或键入属性。使用[Attributes](Attributes.zh-Hans.md)'下标可仅获取单个属性的值：

```swift
selection.attributes(in: text)[\.foregroundColor].contains(.red)
```


---
source: https://developer.apple.com/documentation/SwiftUI/AttributedTextSelection/attributes(in:)
crawled: 2025-12-03T06:17:45Z
---

# attributes(in:)

**Instance Method**

Obtain a lazy sequence of all attribute values the selection has in a given text.

## Declaration

```swift
func attributes(in text: AttributedString) -> AttributedTextSelection.Attributes<AttributedString>
```

## Discussion

The attribute values of a selection are the attribute values of each run that is fully or partially selected, or the typing attributes in the case the selection is an insertion point.

By default, the sequence contains the attribute container for every run or the typing attributes. Use the [Attributes](Attributes.zh-Hans.md)’ subscript to obtain only the values for a single attribute:

```swift
selection.attributes(in: text)[\.foregroundColor].contains(.red)
```

