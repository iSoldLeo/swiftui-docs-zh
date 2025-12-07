---
来源： https://developer.apple.com/documentation/SwiftUI/KeyboardShortcut/Localization-swift.struct/withoutMirroring
抓取时间： 2025-12-04T13:38:11Z
---

# withoutMirroring

**类型属性**

不镜像快捷方式。

## 声明

```swift
static let withoutMirroring: KeyboardShortcut.Localization
```

## 讨论

此快捷键适用于总是具有特定方向性的快捷键，例如向右对齐。

不要将此选项用于导航快捷方式，如 "返回"，因为在从右到左的上下文中，导航是翻转的。

## 获取本地化策略

- **automatic**：将快捷方式重新映射为国际对应快捷方式，并酌情镜像为从右向左的使用方式。
- **custom**：不使用自动快捷方式重映射。


---
source: https://developer.apple.com/documentation/SwiftUI/KeyboardShortcut/Localization-swift.struct/withoutMirroring
crawled: 2025-12-04T13:38:11Z
---

# withoutMirroring

**Type Property**

Don’t mirror shortcuts.

## Declaration

```swift
static let withoutMirroring: KeyboardShortcut.Localization
```

## Discussion

Use this for shortcuts that always have a specific directionality, like aligning something on the right.

Don’t use this option for navigational shortcuts like “Go Back” because navigation is flipped in right-to-left contexts.

## Getting localization strategies

- **automatic**: Remap shortcuts to their international counterparts, mirrored for right-to-left usage if appropriate.
- **custom**: Don’t use automatic shortcut remapping.

