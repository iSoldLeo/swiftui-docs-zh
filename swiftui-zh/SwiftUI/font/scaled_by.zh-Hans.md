--- 来源：https://developer.apple.com/documentation/SwiftUI/Font/scaled(by:)

抓取时间：2025-12-03T06:18:20Z

---

# scaled(by:)

**实例方法**

缩放字体的磅值。

## 声明

```swift
func scaled(by factor: CGFloat) -> Font
```

## 说明

scale 方法的调用是乘法运算，基于已解析字体的大小。例如，

```swift
Font.body
    .scaled(by: 2)
    .bold()
    .scaled(by: 3)
```

会将正文字体加粗至其通常大小的 6 倍。


---
source: https://developer.apple.com/documentation/SwiftUI/Font/scaled(by:)
crawled: 2025-12-03T06:18:20Z
---

# scaled(by:)

**Instance Method**

Scales the point size of the font.

## Declaration

```swift
func scaled(by factor: CGFloat) -> Font
```

## Discussion

Calls to scale are multiplicative, based on the size of the resolved font. For example,

```swift
Font.body
    .scaled(by: 2)
    .bold()
    .scaled(by: 3)
```

results in a bold body font 6x its usual size.

