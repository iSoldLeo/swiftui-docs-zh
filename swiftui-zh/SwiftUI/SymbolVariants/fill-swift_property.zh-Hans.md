--- 来源：https://developer.apple.com/documentation/SwiftUI/SymbolVariants/fill-swift.property

抓取时间：2025-12-03T06:21:26Z

---

# fill

**实例属性**

填充后的变体。

## 声明

```swift
var fill: SymbolVariants { get }
```

## 讨论

使用此属性可以修改形状变体，例如 [circle-swift.type.property](circle-swift_type_property.zh-Hans.md)，使其也填充：

```swift
Label("Circle Fill", systemImage: "flag")
    .symbolVariant(.circle.fill)
```

## 修改变体

- **circle**：圆形封装的变体。

- **square**：正方形封装的变体。

- **rectangle**：一个被矩形框起来的变体版本。

- **slash**：一个带有斜杠的变体版本。


---
source: https://developer.apple.com/documentation/SwiftUI/SymbolVariants/fill-swift.property
crawled: 2025-12-03T06:21:26Z
---

# fill

**Instance Property**

A filled version of the variant.

## Declaration

```swift
var fill: SymbolVariants { get }
```

## Discussion

Use this property to modify a shape variant like [circle-swift.type.property](circle-swift_type_property.zh-Hans.md) so that it’s also filled:

```swift
Label("Circle Fill", systemImage: "flag")
    .symbolVariant(.circle.fill)
```



## Modifying a variant

- **circle**: A version of the variant that’s encapsulated in a circle.
- **square**: A version of the variant that’s encapsulated in a square.
- **rectangle**: A version of the variant that’s encapsulated in a rectangle.
- **slash**: A slashed version of the variant.

