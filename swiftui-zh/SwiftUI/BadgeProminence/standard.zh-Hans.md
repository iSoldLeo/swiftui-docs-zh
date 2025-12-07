--- 来源：https://developer.apple.com/documentation/SwiftUI/BadgeProminence/standard

抓取时间：2025-12-03T06:40:07Z

---

# standard

**类型属性**

徽章的标准突出显示级别。

## 声明

```swift
static let standard: BadgeProminence
```

## 讨论

此突出显示级别适用于显示提示用户操作值的徽章，例如未读邮件数量或新邀请。

在 macOS 的列表中，此级别徽章标签会显示在灰度背景上；而在 iOS 的列表中，此级别徽章标签则没有背景。

```swift
List(mailboxes) { mailbox in
    Text(mailbox.name)
        .badge(mailbox.numberOfUnreadMessages)
}
.badgeProminence(.standard)
```

## 获取背景突出显示级别

- **increased**：徽章的最高突出显示级别。

- **decreased**：徽章的最低级别。


---
source: https://developer.apple.com/documentation/SwiftUI/BadgeProminence/standard
crawled: 2025-12-03T06:40:07Z
---

# standard

**Type Property**

The standard level of prominence for a badge.

## Declaration

```swift
static let standard: BadgeProminence
```

## Discussion

This level of prominence should be used for badges that display a value that suggests user action, such as a count of unread messages or new invitations.

In lists on macOS, this results in a badge label on a grayscale platter; and in lists on iOS, this prominence of badge has no platter.

```swift
List(mailboxes) { mailbox in
    Text(mailbox.name)
        .badge(mailbox.numberOfUnreadMessages)
}
.badgeProminence(.standard)
```

## Getting background prominence

- **increased**: The highest level of prominence for a badge.
- **decreased**: The lowest level of prominence for a badge.

