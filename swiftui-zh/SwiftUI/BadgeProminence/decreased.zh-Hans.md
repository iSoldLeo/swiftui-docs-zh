--- 来源：https://developer.apple.com/documentation/SwiftUI/BadgeProminence/decreased

抓取时间：2025-12-03T06:40:08Z

---

# 降低

**类型属性**

徽章的最低突出显示级别。

## 声明

```swift
static let decreased: BadgeProminence
```

## 讨论

此突出显示级别适用于显示无需用户操作的被动信息的徽章，例如消息或内容的总数。

在 iOS 和 macOS 的列表中，这将使徽章标签以无任何额外装饰的形式显示。在 iOS 上，其外观与 `.standard` 相同。

```swift
List(folders) { folder in
    Text(folder.name)
        .badge(folder.numberOfItems)
}
.badgeProminence(.decreased)
```

## 获取背景突出显示级别

- **standard**：徽章的标准突出显示级别。

- **increased**：徽章的最高级别。


---
source: https://developer.apple.com/documentation/SwiftUI/BadgeProminence/decreased
crawled: 2025-12-03T06:40:08Z
---

# decreased

**Type Property**

The lowest level of prominence for a badge.

## Declaration

```swift
static let decreased: BadgeProminence
```

## Discussion

This level or prominence should be used for badges that display a value of passive information that requires no user action, such as total number of messages or content.

In lists on iOS and macOS, this results in badge labels being displayed without any extra decoration. On iOS, this looks the same as `.standard`.

```swift
List(folders) { folder in
    Text(folder.name)
        .badge(folder.numberOfItems)
}
.badgeProminence(.decreased)
```

## Getting background prominence

- **standard**: The standard level of prominence for a badge.
- **increased**: The highest level of prominence for a badge.

