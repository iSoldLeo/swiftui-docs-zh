---
来源： https://developer.apple.com/documentation/SwiftUI/GeometryEffect/ignoredByLayout()
抓取时间： 2025-12-01T11:04:56Z
---

# ignoredByLayout()

**实例方法**

返回一个与此特效产生相同几何变换的特效，但只在渲染视图时应用该变换。

## 声明

```swift
func ignoredByLayout() -> _IgnoredByLayoutEffect<Self>
```

## 讨论

使用此方法可以在转换过程中禁用布局变化。在视图执行布局计算时，视图会忽略此方法返回的变换。

## 应用效果

- **effectValue(size:)**：返回特效的当前值。


---
source: https://developer.apple.com/documentation/SwiftUI/GeometryEffect/ignoredByLayout()
crawled: 2025-12-01T11:04:56Z
---

# ignoredByLayout()

**Instance Method**

Returns an effect that produces the same geometry transform as this effect, but only applies the transform while rendering its view.

## Declaration

```swift
func ignoredByLayout() -> _IgnoredByLayoutEffect<Self>
```

## Discussion

Use this method to disable layout changes during transitions. The view ignores the transform returned by this method while the view is performing its layout calculations.

## Applying effects

- **effectValue(size:)**: Returns the current value of the effect.

