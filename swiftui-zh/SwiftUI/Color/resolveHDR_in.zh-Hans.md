---
来源： https://developer.apple.com/documentation/SwiftUI/Color/resolveHDR(in:)
抓取时间： 2025-12-01T10:29:05Z
---

# resolveHDR(in:)

**实例方法**

在给定一组环境值的情况下，将此颜色评估为具有内容余量的解析颜色。

## 声明

```swift
func resolveHDR(in environment: EnvironmentValues) -> Color.ResolvedHDR
```

## 参数

- **environment**：显示颜色的视图环境。

## 返回值

颜色在 sRGB 色彩空间中的值。

## 处理高动态范围 (HDR) 颜色

- **Color.ResolvedHDR**：具体的颜色值，包括 HDR 净空信息。


---
source: https://developer.apple.com/documentation/SwiftUI/Color/resolveHDR(in:)
crawled: 2025-12-01T10:29:05Z
---

# resolveHDR(in:)

**Instance Method**

Evaluates this color to a resolved color with content headroom, given a set of environment values.

## Declaration

```swift
func resolveHDR(in environment: EnvironmentValues) -> Color.ResolvedHDR
```

## Parameters

- **environment**: The environment of the view displaying the color.

## Return Value

The color’s value in the sRGB color space.

## Working with high dynamic range (HDR) colors

- **Color.ResolvedHDR**: A concrete color value, including HDR headroom information.

