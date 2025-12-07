---
来源：https://developer.apple.com/documentation/SwiftUI/GridItem/Size-swift.enum/flexible(最小值:最大值:)
抓取时间： 2025-12-04T13:32:26Z
---

# GridItem.Size.flexible(minimum:maximum:)

**Case**

单个灵活项。

## 声明

```swift
case flexible(minimum: CGFloat = 10, maximum: CGFloat = .infinity)
```

## 讨论

该项的大小是去掉间距和不灵活项后的网格大小，除以灵活项的数量，并夹在所提供的边界内。

## 获取尺寸

- **GridItem.Size.adaptive(minimum:maximum:)**：单个灵活项目空间中的多个项目。
- **GridItem.Size.fixed(_:)**：具有指定固定尺寸的单个项目。


---
source: https://developer.apple.com/documentation/SwiftUI/GridItem/Size-swift.enum/flexible(minimum:maximum:)
crawled: 2025-12-04T13:32:26Z
---

# GridItem.Size.flexible(minimum:maximum:)

**Case**

A single flexible item.

## Declaration

```swift
case flexible(minimum: CGFloat = 10, maximum: CGFloat = .infinity)
```

## Discussion

The size of this item is the size of the grid with spacing and inflexible items removed, divided by the number of flexible items, clamped to the provided bounds.

## Getting the sizes

- **GridItem.Size.adaptive(minimum:maximum:)**: Multiple items in the space of a single flexible item.
- **GridItem.Size.fixed(_:)**: A single item with the specified fixed size.

