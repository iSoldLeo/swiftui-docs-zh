--- 来源：https://developer.apple.com/documentation/SwiftUI/EditMode/transient
抓取时间：2025-12-03T06:40:11Z

---

# EditMode.transient

**Case**

视图处于临时编辑模式。

## 声明

```swift
case transient
```

## 讨论

此状态的使用因平台和控件而异。例如，SwiftUI 可能会在滑动操作期间启用临时编辑模式。

在此状态下，[isEditing](isEditing.zh-Hans.md) 属性为 `true`。

## 获取编辑模式

- **EditMode.active**：用户可以编辑视图内容。

- **EditMode.inactive**：用户无法编辑视图内容。


---
source: https://developer.apple.com/documentation/SwiftUI/EditMode/transient
crawled: 2025-12-03T06:40:11Z
---

# EditMode.transient

**Case**

The view is in a temporary edit mode.

## Declaration

```swift
case transient
```

## Discussion

The use of this state varies by platform and for different controls. As an example, SwiftUI might engage temporary edit mode over the duration of a swipe gesture.

The [isEditing](isEditing.zh-Hans.md) property is `true` in this state.

## Getting edit modes

- **EditMode.active**: The user can edit the view content.
- **EditMode.inactive**: The user can’t edit the view content.

