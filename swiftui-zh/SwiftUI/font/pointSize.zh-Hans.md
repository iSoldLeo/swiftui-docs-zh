--- 来源：https://developer.apple.com/documentation/SwiftUI/Font/pointSize(_:)

抓取时间：2025-12-01T11:07:28Z

---

# pointSize(_:)

**实例方法**

显式设置字体的磅值。

## 声明

```swift
func pointSize(_ size: CGFloat) -> Font
```

## 说明

显式设置磅值会导致基于样式的字体不再随设备的默认文本大小缩放。要使字体大小相对于其当前大小进行缩放，请参阅 [scaled(by:)](scaled_by.zh-Hans.md)。


---
source: https://developer.apple.com/documentation/SwiftUI/Font/pointSize(_:)
crawled: 2025-12-01T11:07:28Z
---

# pointSize(_:)

**Instance Method**

Sets the point size of the font explicitly.

## Declaration

```swift
func pointSize(_ size: CGFloat) -> Font
```

## Discussion

Setting the point size explicitly will result in style based fonts no longer scaling with the device’s preferred text size. To scale a font’s size relative to its current size, see [scaled(by:)](scaled_by.zh-Hans.md).

