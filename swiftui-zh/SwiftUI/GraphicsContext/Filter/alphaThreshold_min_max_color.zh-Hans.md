---
来源：https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Filter/alphaThreshold(min:max:color:)
抓取时间：2025-12-03T17:20:36Z
---

# alphaThreshold(min:max:color:)

**类型方法**

返回一个过滤器，在一定范围内用常量颜色替换具有 alpha 分量的每个像素，否则返回透明度。

## 声明

```swift
static func alphaThreshold(min: Double, max: Double = 1, color: Color = Color.black) -> GraphicsContext.Filter
```

## 参数

- **min**：最小 alpha 阈值。Alpha 分量小于此值的像素将呈现为透明。除非使用 `min < max`，否则结果未定义。
- **max**：最大 Alpha 阈值。Alpha 分量大于此值的像素将呈现为透明。除非 `min < max`，否则结果是未定义的。
- **color**：像素的 alpha 分量介于两个阈值之间时输出的颜色。

## 返回值

对 alpha 值应用阈值的过滤器。

## 调整不透明度

- **luminanceToAlpha**：返回一个根据像素亮度设置像素不透明度的滤镜。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Filter/alphaThreshold(min:max:color:)
crawled: 2025-12-03T17:20:36Z
---

# alphaThreshold(min:max:color:)

**Type Method**

Returns a filter that replaces each pixel with alpha components within a range by a constant color, or transparency otherwise.

## Declaration

```swift
static func alphaThreshold(min: Double, max: Double = 1, color: Color = Color.black) -> GraphicsContext.Filter
```

## Parameters

- **min**: The minimum alpha threshold. Pixels whose alpha component is less than this value will render as transparent. Results are undefined unless `min < max`.
- **max**: The maximum alpha threshold. Pixels whose alpha component is greater than this value will render as transparent. Results are undefined unless `min < max`.
- **color**: The color that is output for pixels with an alpha component between the two threshold values.

## Return Value

A filter that applies a threshold to alpha values.

## Adjusting opacity

- **luminanceToAlpha**: Returns a filter that sets the opacity of each pixel based on its luminance.

