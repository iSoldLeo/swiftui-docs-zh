--- 来源：https://developer.apple.com/documentation/SwiftUI/TextRenderer/displayPadding
抓取时间：2025-12-02T20:59:21Z

---

# displayPadding

**实例属性**

返回添加到用于栅格化文本的任何绘图图层的额外内边距的大小。例如，在绘制带有阴影的文本时，可以使用此属性扩展绘图边界，以避免阴影被裁剪。

## 声明

```swift
var displayPadding: EdgeInsets { get }
```

## 讨论

此函数的默认实现返回一个空的内边距集合。


---
source: https://developer.apple.com/documentation/SwiftUI/TextRenderer/displayPadding
crawled: 2025-12-02T20:59:21Z
---

# displayPadding

**Instance Property**

Returns the size of the extra padding added to any drawing layer used to rasterize the text. For example when drawing the text with a shadow this may be used to extend the drawing bounds to avoid clipping the shadow.

## Declaration

```swift
var displayPadding: EdgeInsets { get }
```

## Discussion

The default implementation of this function returns an empty set of insets.

