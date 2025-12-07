--- 来源：https://developer.apple.com/documentation/SwiftUI/Shader/dithersColor
抓取时间：2025-12-03T06:34:00Z

---

# dithersColor

**实例属性**

对于返回颜色值的着色器函数，此属性用于控制返回的颜色是否添加了抖动噪声，或者只是简单地四舍五入到输出位深度。对于生成平滑渐变的着色器，通常需要使用抖动来防止结果中出现可见的条带。

## 声明

```swift
var dithersColor: Bool { get set }
```


---
source: https://developer.apple.com/documentation/SwiftUI/Shader/dithersColor
crawled: 2025-12-03T06:34:00Z
---

# dithersColor

**Instance Property**

For shader functions that return color values, whether the returned color has dither noise added to it, or is simply rounded to the output bit-depth. For shaders generating smooth gradients, dithering is usually necessary to prevent visible banding in the result.

## Declaration

```swift
var dithersColor: Bool { get set }
```

