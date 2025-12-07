--- 来源：https://developer.apple.com/documentation/SwiftUI/HorizontalAlignment/listRowSeparatorLeading
抓取时间：2025-12-03T06:36:40Z

---

# listRowSeparatorLeading

**类型属性**

用于标记行分隔符`List`前缘的参考线。

## 声明

```swift
static let listRowSeparatorLeading: HorizontalAlignment
```

## 说明

使用此参考线可将底部行分隔符`List`的前缘与单元格内容视图中的任何其他水平参考线对齐。

以下示例显示了与包含食物名称的 `Text` 的前缘对齐的行分隔符：

```swift
List {
    ForEach(favoriteFoods) { food in
        HStack {
            Text(food.emoji)
                .font(.system(size: 40))
            Text(food.name)
                .alignmentGuide(.listRowSeparatorLeading) {
                    $0[.leading]
                }
        }
    }
}
```

要更改行分隔符的可见性或色调，请分别使用 [listRowSeparator(_:edges:)](../View/listRowSeparator___edges.zh-Hans.md) 和 [listRowSeparatorTint(_:edges:)](../View/listRowSeparatorTint___edges.zh-Hans.md)。

## 获取参考线

- **leading**：标记视图前缘的参考线。

- **center**：标记视图水平中心的参考线。

- **trailing**：标记视图后缘的参考线。

- **listRowSeparatorTrailing**：标记 `List` 行分隔符后缘的参考线。


---
source: https://developer.apple.com/documentation/SwiftUI/HorizontalAlignment/listRowSeparatorLeading
crawled: 2025-12-03T06:36:40Z
---

# listRowSeparatorLeading

**Type Property**

A guide marking the leading edge of a `List` row separator.

## Declaration

```swift
static let listRowSeparatorLeading: HorizontalAlignment
```

## Discussion

Use this guide to align the leading end of the bottom `List` row separator with any other horizontal guide of a view that is part of the cell content.

The following example shows the row separator aligned with the leading edge of the `Text` containing the name of food:

```swift
List {
    ForEach(favoriteFoods) { food in
        HStack {
            Text(food.emoji)
                .font(.system(size: 40))
            Text(food.name)
                .alignmentGuide(.listRowSeparatorLeading) {
                    $0[.leading]
                }
        }
    }
}
```

To change the visibility or tint of the row separator use respectively [listRowSeparator(_:edges:)](../View/listRowSeparator___edges.zh-Hans.md) and [listRowSeparatorTint(_:edges:)](../View/listRowSeparatorTint___edges.zh-Hans.md).

## Getting guides

- **leading**: A guide that marks the leading edge of the view.
- **center**: A guide that marks the horizontal center of the view.
- **trailing**: A guide that marks the trailing edge of the view.
- **listRowSeparatorTrailing**: A guide marking the trailing edge of a `List` row separator.

