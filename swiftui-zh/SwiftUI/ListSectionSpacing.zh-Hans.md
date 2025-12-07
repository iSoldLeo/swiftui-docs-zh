--- 来源：https://developer.apple.com/documentation/SwiftUI/ListSectionSpacing

抓取时间：2025-12-02T17:39:31Z

---

# ListSectionSpacing

**Structure**

列表中相邻两个分区之间的间距选项。

## 声明

```swift
struct ListSectionSpacing
```

## 获取分区间距

- **default**：分区之间的默认间距

- **compact**：分区之间的紧凑间距

- **custom(_:)**：创建自定义间距值。

## 配置列表布局

- **listRowInsets(_:)**：为列表中的行应用内边距。

- **defaultMinListRowHeight**：列表行的默认最小高度。

- **defaultMinListHeaderHeight**：列表标题的默认最小高度。

- **listRowSpacing(_:)**：设置列表中相邻两行之间的垂直间距。

- **listSectionSpacing(_:)**：将 [List](List.zh-Hans.md) 中相邻部分之间的间距设置为自定义值。

- **listSectionMargins(_:_:)**：设置特定边缘的部分边距。

## 符合以下标准

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/ListSectionSpacing
crawled: 2025-12-02T17:39:31Z
---

# ListSectionSpacing

**Structure**

The spacing options between two adjacent sections in a list.

## Declaration

```swift
struct ListSectionSpacing
```

## Getting section spacing

- **default**: The default spacing between sections
- **compact**: Compact spacing between sections
- **custom(_:)**: Creates a custom spacing value.

## Configuring a list’s layout

- **listRowInsets(_:)**: Applies an inset to the rows in a list.
- **defaultMinListRowHeight**: The default minimum height of rows in a list.
- **defaultMinListHeaderHeight**: The default minimum height of a header in a list.
- **listRowSpacing(_:)**: Sets the vertical spacing between two adjacent rows in a List.
- **listSectionSpacing(_:)**: Sets the spacing between adjacent sections in a [List](List.zh-Hans.md) to a custom value.
- **listSectionMargins(_:_:)**: Set the section margins for the specific edges.

## Conforms To

- Sendable
- SendableMetatype

