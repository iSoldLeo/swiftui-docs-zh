---
来源： https://developer.apple.com/documentation/SwiftUI/PresentationAdaptation/automatic
抓取时间： 2025-12-03T06:02:04Z
---

# 自动

**类型属性**

使用默认的演示适应。

## 声明

```swift
static var automatic: PresentationAdaptation { get }
```

## 获取适应战略

- **none**：如果可能，不要为大小级别进行调整。
- **fullScreenCover**：为尺寸类别适配时，首选全屏封面外观。
- **popover**：在适应大小类别时，首选弹出式外观。
- **sheet**：在适应尺寸类别时，首选工作表外观。


---
source: https://developer.apple.com/documentation/SwiftUI/PresentationAdaptation/automatic
crawled: 2025-12-03T06:02:04Z
---

# automatic

**Type Property**

Use the default presentation adaptation.

## Declaration

```swift
static var automatic: PresentationAdaptation { get }
```

## Getting adaptation strategies

- **none**: Don’t adapt for the size class, if possible.
- **fullScreenCover**: Prefer a full-screen-cover appearance when adapting for size classes.
- **popover**: Prefer a popover appearance when adapting for size classes.
- **sheet**: Prefer a sheet appearance when adapting for size classes.

