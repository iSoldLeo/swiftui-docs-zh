--- 来源：https://developer.apple.com/documentation/SwiftUI/BadgeProminence/increased

抓取时间：2025-12-03T06:40:07Z

---

# 增加

**类型属性**

徽章的最高突出显示级别。

## 声明

```swift
static let increased: BadgeProminence
```

## 讨论

此突出显示级别适用于显示需要用户操作的值的徽章，例如更新次数或帐户错误。

在 iOS 和 macOS 的列表中，这将导致徽章标签显示在红色背景上。

```swift
ForEach(accounts) { account in
    Text(account.userName)
        .badge(account.setupErrors)
        .badgeProminence(.increased)
}
```

## 获取背景突出显示级别

- **standard**：徽章的标准突出显示级别。

- **decreased**：徽章的最低级别。


---
source: https://developer.apple.com/documentation/SwiftUI/BadgeProminence/increased
crawled: 2025-12-03T06:40:07Z
---

# increased

**Type Property**

The highest level of prominence for a badge.

## Declaration

```swift
static let increased: BadgeProminence
```

## Discussion

This level of prominence should be used for badges that display a value that requires user action, such as number of updates or account errors.

In lists on iOS and macOS, this results in badge labels being displayed on a red platter.

```swift
ForEach(accounts) { account in
    Text(account.userName)
        .badge(account.setupErrors)
        .badgeProminence(.increased)
}
```

## Getting background prominence

- **standard**: The standard level of prominence for a badge.
- **decreased**: The lowest level of prominence for a badge.

