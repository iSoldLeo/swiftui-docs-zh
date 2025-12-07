---
来源： https://developer.apple.com/documentation/SwiftUI/LayoutDirectionBehavior/mirrors(in:)
抓取时间： 2025-12-03T06:37:17Z
---

# LayoutDirectionBehavior.mirrors(in:)

**Case**

当布局方向具有指定值时，镜像的行为。

### 声明

```swift
case mirrors(in: LayoutDirection)
```

## 讨论

如果在 LTR 上下文中开发视图或形状，可以使用 `.mirrors(in: .rightToLeft)`（相当于 `.mirrors`）在布局方向为 RTL 时镜像内容（并在 LTR 中保留原始版本）。如果您在 RTL 上下文中进行开发，则可以使用`.mirrors(in: .leftToRight)` 在布局方向为 LTR 时镜像您的内容（并在 RTL 中保留原始版本）。

## 获取行为

- **LayoutDirectionBehavior.fixed**：当布局方向改变时不进行镜像的行为。
- **mirrors**：当布局方向为从右到左时会镜像的行为。


---
source: https://developer.apple.com/documentation/SwiftUI/LayoutDirectionBehavior/mirrors(in:)
crawled: 2025-12-03T06:37:17Z
---

# LayoutDirectionBehavior.mirrors(in:)

**Case**

A behavior that mirrors when the layout direction has the specified value.

## Declaration

```swift
case mirrors(in: LayoutDirection)
```

## Discussion

If you develop your view or shape in an LTR context, you can use `.mirrors(in: .rightToLeft)` (which is equivalent to `.mirrors`) to mirror your content when the layout direction is RTL (and keep the original version in LTR). If you developer in an RTL context, you can use `.mirrors(in: .leftToRight)` to mirror your content when the layout direction is LTR (and keep the original version in RTL).

## Getting behaviors

- **LayoutDirectionBehavior.fixed**: A behavior that doesn’t mirror when the layout direction changes.
- **mirrors**: A behavior that mirrors when the layout direction is right-to-left.

