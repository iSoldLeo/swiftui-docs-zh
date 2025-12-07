--- 来源：https://developer.apple.com/documentation/SwiftUI/ListItemTint/preferred(_:)

抓取时间：2025-12-01T11:29:17Z

---

# preferred(_:)

**类型方法**

一种显式着色颜色，系统可以覆盖此颜色。

## 声明

```swift
static func preferred(_ tint: Color) -> ListItemTint
```

## 参数

- **tint**：用于着色内容的颜色。

## 讨论

系统可以覆盖此着色效果，例如当系统在 macOS 上设置了自定义用户强调色时。

## 获取列表项着色选项

- **monochrome**：标准的灰度着色效果。

- **fixed(_:)**：显式着色颜色。


---
source: https://developer.apple.com/documentation/SwiftUI/ListItemTint/preferred(_:)
crawled: 2025-12-01T11:29:17Z
---

# preferred(_:)

**Type Method**

An explicit tint color that the system can override.

## Declaration

```swift
static func preferred(_ tint: Color) -> ListItemTint
```

## Parameters

- **tint**: The color to use to tint the content.

## Discussion

The system can override this tint effect, like when the system has a custom user accent color on macOS.

## Getting list item tint options

- **monochrome**: A standard grayscale tint effect.
- **fixed(_:)**: An explicit tint color.

