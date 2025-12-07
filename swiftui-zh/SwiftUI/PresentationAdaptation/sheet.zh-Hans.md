---
来源： https://developer.apple.com/documentation/SwiftUI/PresentationAdaptation/sheet
抓取时间： 2025-12-03T06:02:07Z
---

#张

**类型属性**

在调整尺寸类别时，首选工作表外观。

## 声明

```swift
static var sheet: PresentationAdaptation { get }
```

## 获取适应战略

- **automatic**：使用默认的演示适配。
- **none**：如果可能，不要对尺寸类别进行适配。
- **fullScreenCover**：为尺寸类别适配时，首选全屏封面外观。
- **popover**：在适应大小类别时，首选弹出式外观。


---
source: https://developer.apple.com/documentation/SwiftUI/PresentationAdaptation/sheet
crawled: 2025-12-03T06:02:07Z
---

# sheet

**Type Property**

Prefer a sheet appearance when adapting for size classes.

## Declaration

```swift
static var sheet: PresentationAdaptation { get }
```

## Getting adaptation strategies

- **automatic**: Use the default presentation adaptation.
- **none**: Don’t adapt for the size class, if possible.
- **fullScreenCover**: Prefer a full-screen-cover appearance when adapting for size classes.
- **popover**: Prefer a popover appearance when adapting for size classes.

