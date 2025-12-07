---
来源: https://developer.apple.com/documentation/SwiftUI/GridItem/Size-swift.enum/adaptive(最小值:最大值:)
抓取时间：2025-12-04T13:32:24Z
---

# GridItem.Size.adaptive(minimum:maximum:)

**Case**

在单个灵活项的空间中显示多个项。

## 声明

```swift
case adaptive(minimum: CGFloat, maximum: CGFloat = .infinity)
```

## 讨论

这种尺寸情况会将一个或多个项目放入分配给单个`flexible` 项目的空间，并使用所提供的边界和间距来决定到底有多少项目可以放入。这种方法倾向于插入尽可能多的`minimum`大小的项，但允许它们增加到`maximum`大小。

## 获取大小

- **GridItem.Size.fixed(_:)**：具有指定固定大小的单个项目。
- **GridItem.Size.flexible(minimum:maximum:)**：单个柔性项目。


---
source: https://developer.apple.com/documentation/SwiftUI/GridItem/Size-swift.enum/adaptive(minimum:maximum:)
crawled: 2025-12-04T13:32:24Z
---

# GridItem.Size.adaptive(minimum:maximum:)

**Case**

Multiple items in the space of a single flexible item.

## Declaration

```swift
case adaptive(minimum: CGFloat, maximum: CGFloat = .infinity)
```

## Discussion

This size case places one or more items into the space assigned to a single `flexible` item, using the provided bounds and spacing to decide exactly how many items fit. This approach prefers to insert as many items of the `minimum` size as possible but lets them increase to the `maximum` size.

## Getting the sizes

- **GridItem.Size.fixed(_:)**: A single item with the specified fixed size.
- **GridItem.Size.flexible(minimum:maximum:)**: A single flexible item.

