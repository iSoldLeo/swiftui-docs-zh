--- 来源：https://developer.apple.com/documentation/SwiftUI/RoundedRectangularShape/corners(in:)

抓取时间：2025-12-03T05:38:14Z

---

# corners(in:)

**实例方法**

根据尺寸解析圆角。如果形状的圆角样式取决于尺寸，则读取提供的尺寸并相应地返回值。当尺寸未确定时，可以传入 nil 值来调用此函数。在这种情况下，返回最佳近似值。例如，对于胶囊形状，其圆角半径由尺寸决定。如果尺寸不可用，则返回 `.fixed(.infinity)` 表示圆角应尽可能圆润。

## 声明

```swift
func corners(in size: CGSize?) -> Self.Corners?
```


---
source: https://developer.apple.com/documentation/SwiftUI/RoundedRectangularShape/corners(in:)
crawled: 2025-12-03T05:38:14Z
---

# corners(in:)

**Instance Method**

Resolved corners given a size. If the corner style of a shape is size-dependent, read the provided size and return values accordingly. This function could be called with a nil size when the size hasn’t been determined. In that case, return the best approximated value. For example, for a capsule shape, its corner radius is determined by the size. If size is not available, return `.fixed(.infinity)` to indicate that the corner should be as round as it could be.

## Declaration

```swift
func corners(in size: CGSize?) -> Self.Corners?
```

