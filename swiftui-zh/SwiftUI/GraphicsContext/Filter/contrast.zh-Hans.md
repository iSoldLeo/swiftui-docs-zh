---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Filter/contrast(_:)
抓取时间： 2025-12-01T22:05:45Z
---

# contrast(_:)

**类型方法**

返回应用对比度调整的过滤器。

## 声明

```swift
static func contrast(_ amount: Double) -> GraphicsContext.Filter
```

## 参数

- **amount**：用于调整对比度的数值。值为 0 时，结果为完全灰色。值为 1 时，结果保持不变。您可以使用大于 1 的值。

## 返回值

应用对比度调整的滤镜。

## 讨论

该滤波器等同于可缩放矢量图形（SVG）规范定义的`contrast`滤波器基元。

## 更改亮度和对比度

- **brightness(_:)**：返回应用亮度调整的滤镜。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Filter/contrast(_:)
crawled: 2025-12-01T22:05:45Z
---

# contrast(_:)

**Type Method**

Returns a filter that applies a contrast adjustment.

## Declaration

```swift
static func contrast(_ amount: Double) -> GraphicsContext.Filter
```

## Parameters

- **amount**: An amount to adjust the contrast. A value of zero leaves the result completely gray. A value of one leaves the result unchanged. You can use values greater than one.

## Return Value

A filter that applies a contrast adjustment.

## Discussion

This filter is equivalent to the `contrast` filter primitive defined by the Scalable Vector Graphics (SVG) specification.

## Changing brightness and contrast

- **brightness(_:)**: Returns a filter that applies a brightness adjustment.

