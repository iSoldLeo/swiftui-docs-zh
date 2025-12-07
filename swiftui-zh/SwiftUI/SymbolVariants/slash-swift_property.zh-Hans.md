--- 来源：https://developer.apple.com/documentation/SwiftUI/SymbolVariants/slash-swift.property

抓取时间：2025-12-03T06:21:27Z

---

# 斜杠

**实例属性**

带斜杠的变体版本。

## 声明

```swift
var slash: SymbolVariants { get }
```

## 讨论

使用此属性修改形状变体，例如 [circle-swift.type.property](circle-swift_type_property.zh-Hans.md)，使其也被斜杠覆盖：

```swift
Label("Circle Slash", systemImage: "flag")
    .symbolVariant(.circle.slash)
```

## 修改变体

- **circle**：圆形封装的变体版本。

- **square**：正方形封装的变体版本。

- **rectangle**：矩形框内的变体版本。

- **fill**：填充后的变体版本。


---
source: https://developer.apple.com/documentation/SwiftUI/SymbolVariants/slash-swift.property
crawled: 2025-12-03T06:21:27Z
---

# slash

**Instance Property**

A slashed version of the variant.

## Declaration

```swift
var slash: SymbolVariants { get }
```

## Discussion

Use this property to modify a shape variant like [circle-swift.type.property](circle-swift_type_property.zh-Hans.md) so that it’s also covered by a slash:

```swift
Label("Circle Slash", systemImage: "flag")
    .symbolVariant(.circle.slash)
```



## Modifying a variant

- **circle**: A version of the variant that’s encapsulated in a circle.
- **square**: A version of the variant that’s encapsulated in a square.
- **rectangle**: A version of the variant that’s encapsulated in a rectangle.
- **fill**: A filled version of the variant.

