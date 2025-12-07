--- 来源：https://developer.apple.com/documentation/SwiftUI/SymbolVariants/circle-swift.property

抓取时间：2025-12-03T06:21:24Z

---

# circle

**实例属性**

一个包含在圆形内的变体版本。

## 声明

```swift
var circle: SymbolVariants { get }
```

## 讨论

使用此属性可以修改类似 [fill-swift.property](fill-swift_property.zh-Hans.md) 的变体，使其也包含在圆形内：

```swift
Label("Fill Circle", systemImage: "bolt")
    .symbolVariant(.fill.circle)
```

## 修改变体

- **square**：一个包含在正方形内的变体版本。

- **rectangle**：一个包含在矩形内的变体版本。

- **fill**：此变体的填充版本。

- **slash**：此变体的斜杠版本。


---
source: https://developer.apple.com/documentation/SwiftUI/SymbolVariants/circle-swift.property
crawled: 2025-12-03T06:21:24Z
---

# circle

**Instance Property**

A version of the variant that’s encapsulated in a circle.

## Declaration

```swift
var circle: SymbolVariants { get }
```

## Discussion

Use this property to modify a variant like [fill-swift.property](fill-swift_property.zh-Hans.md) so that it’s also contained in a circle:

```swift
Label("Fill Circle", systemImage: "bolt")
    .symbolVariant(.fill.circle)
```



## Modifying a variant

- **square**: A version of the variant that’s encapsulated in a square.
- **rectangle**: A version of the variant that’s encapsulated in a rectangle.
- **fill**: A filled version of the variant.
- **slash**: A slashed version of the variant.

