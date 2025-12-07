--- 来源：https://developer.apple.com/documentation/SwiftUI/View/listSectionIndexVisibility(_:)

抓取时间：2025-11-30T21:09:15Z

---

# listSectionIndexVisibility(_:)

**实例方法**

更改列表分区索引的可见性。

## 声明

```swift
nonisolated func listSectionIndexVisibility(_ visibility: Visibility) -> some View

```

## 参数

- **visibility**：列表分区索引的可见性。

## 说明

分区索引显示分区的索引标签，这些标签使用 `sectionIndexLabel` 修饰符设置。这些标签通常是字母，用于已排序的分区。

```swift
List(sections) { section in
    Section(section.title) {
        ForEach(section.rows) { row in
            // ...
        }
    }
    .sectionIndexLabel(section.indexTitle)
}
.listSectionIndexVisibility(.visible)
```

在 iOS 上，分区索引显示在列表末尾，以垂直堆叠的字母数量表示。用户可以通过点击相应的索引标签跳转到列表中的特定部分。

在 watchOS 系统中，当用户使用表冠滚动列表时，当前可见部分的索引会显示在滚动指示器旁边。

默认情况下，如果列表中包含任何带有索引标签的部分，则列表部分索引会显示。

索引仅显示带有 `sectionIndexLabel` 修饰符的部分的标签。这可用于从索引中隐藏某些部分。

通过隐藏带有索引标签的空部分的标题，可以使列表部分索引显示没有对应部分的索引标签。

## 配置部分索引

- **sectionIndexLabel(_:)**：设置用于部分索引的标签，指向当前部分，通常只有一个字符。


---
source: https://developer.apple.com/documentation/SwiftUI/View/listSectionIndexVisibility(_:)
crawled: 2025-11-30T21:09:15Z
---

# listSectionIndexVisibility(_:)

**Instance Method**

Changes the visibility of the list section index.

## Declaration

```swift
nonisolated func listSectionIndexVisibility(_ visibility: Visibility) -> some View

```

## Parameters

- **visibility**: The visibility of the list section index.

## Discussion

The section index shows the section index labels of sections, which are set using the `sectionIndexLabel` modifier. These are typically the letters of the alphabet, used for sorted sections.

```swift
List(sections) { section in
    Section(section.title) {
        ForEach(section.rows) { row in
            // ...
        }
    }
    .sectionIndexLabel(section.indexTitle)
}
.listSectionIndexVisibility(.visible)
```

On iOS, the section index is displayed as a number of vertically stacked letters on the trailing side of the list. Users can jump to a specific section in the list by tapping on the corresponding index label.



On watchOS, the index of the section currently visible is displayed next to the scroll indicator when the user is scrolling through the list using the crown.



By default, the list section index is visible if the list contains any sections with an index label.

The index only shows labels for sections with a `sectionIndexLabel` modifier. This can be used to hide certain sections from the index.

By hiding section headers of empty sections with an index label, a list section index can be made to show index labels without a corresponding section.

## Configuring a section index

- **sectionIndexLabel(_:)**: Sets the label that is used in a section index to point to this section, typically only a single character long.

