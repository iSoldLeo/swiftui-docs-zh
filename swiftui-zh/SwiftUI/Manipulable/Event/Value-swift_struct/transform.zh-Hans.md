---
来源： https://developer.apple.com/documentation/SwiftUI/Manipulable/Event/Value-swift.struct/transform
抓取时间： 2025-12-04T16:54:58Z
---

# 转换

**实例属性**

被操作视图的三维仿射变换，如果视图没有定义明确的三维仿射变换，则使用 `nil`。

### 声明

```swift
let transform: AffineTransform3D?
```

## 讨论

视图可能没有定义明确的三维仿射变换，例如当它受到投影变换的影响时。

这种变换是在视图修改器中配置的坐标空间中进行的。


---
source: https://developer.apple.com/documentation/SwiftUI/Manipulable/Event/Value-swift.struct/transform
crawled: 2025-12-04T16:54:58Z
---

# transform

**Instance Property**

The 3D affine transform of the manipulated view, or `nil` if the view doesn’t have a well-defined 3D affine transfrorm.

## Declaration

```swift
let transform: AffineTransform3D?
```

## Discussion

A view may not have a well-defined 3D affine transform e.g. when it’s affected by a projection transform.

This transform is in the coordinate space configured in the view modifier.

