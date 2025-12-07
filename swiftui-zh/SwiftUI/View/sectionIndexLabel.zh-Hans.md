--- 来源：https://developer.apple.com/documentation/SwiftUI/View/sectionIndexLabel(_:)

抓取时间：2025-12-02T17:25:21Z

---

# sectionIndexLabel(_:)

**实例方法**

设置用于在节索引中指向当前节的标签，通常只有一个字符。

## 声明

```swift
nonisolated func sectionIndexLabel(_ label: Text?) -> some View

```

## 参数

- **label**：要在节索引中显示的标签，或者 `nil`：不显示此节的标签。

## 讨论

- 另请参阅 `listSectionIndexVisibility(_:)`

## 配置节索引

- **listSectionIndexVisibility(_:)**：更改列表节索引的可见性。


---
source: https://developer.apple.com/documentation/SwiftUI/View/sectionIndexLabel(_:)
crawled: 2025-12-02T17:25:21Z
---

# sectionIndexLabel(_:)

**Instance Method**

Sets the label that is used in a section index to point to this section, typically only a single character long.

## Declaration

```swift
nonisolated func sectionIndexLabel(_ label: Text?) -> some View

```

## Parameters

- **label**: The label to display in the section index, or `nil` to display no label for this section.

## Discussion

- See also `listSectionIndexVisibility(_:)`

## Configuring a section index

- **listSectionIndexVisibility(_:)**: Changes the visibility of the list section index.

