---
来源： https://developer.apple.com/documentation/SwiftUI/KeyboardShortcut/Localization-swift.struct/custom
抓取时间： 2025-12-04T13:38:10Z
---

# 自定义

**类型属性**

不使用自动快捷方式重映射。

## 声明

```swift
static let custom: KeyboardShortcut.Localization
```

## 讨论

使用这种模式时，必须分别考虑国际用例。

## 获取本地化策略

- **automatic**：将快捷方式重新映射为国际对应快捷方式，并根据情况从右向左镜像使用。
- **withoutMirroring**：不要镜像快捷方式。


---
source: https://developer.apple.com/documentation/SwiftUI/KeyboardShortcut/Localization-swift.struct/custom
crawled: 2025-12-04T13:38:10Z
---

# custom

**Type Property**

Don’t use automatic shortcut remapping.

## Declaration

```swift
static let custom: KeyboardShortcut.Localization
```

## Discussion

When you use this mode, you have to take care of international use-cases separately.

## Getting localization strategies

- **automatic**: Remap shortcuts to their international counterparts, mirrored for right-to-left usage if appropriate.
- **withoutMirroring**: Don’t mirror shortcuts.

