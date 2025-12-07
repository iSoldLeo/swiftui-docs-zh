--- 来源：https://developer.apple.com/documentation/SwiftUI/SymbolVariants/rectangle-swift.property

抓取时间：2025-12-03T06:21:25Z

---

# rectangle

**实例属性**

一个封装在矩形中的变体版本。

## 声明

```swift
var rectangle: SymbolVariants { get }
```

## 讨论

使用此属性可以修改类似 [fill-swift.property](fill-swift_property.zh-Hans.md) 的变体，使其也包含在矩形中：

```swift
Label("Fill Rectangle", systemImage: "plus")
    .symbolVariant(.fill.rectangle)
```

## 修改变体

- **circle**：一个封装在圆形中的变体版本。

- **square**：一个封装在正方形中的变体版本。

- **fill**：此变体的填充版本。

- **slash**：此变体的斜杠版本。


---
source: https://developer.apple.com/documentation/SwiftUI/SymbolVariants/rectangle-swift.property
crawled: 2025-12-03T06:21:25Z
---

# rectangle

**Instance Property**

A version of the variant that’s encapsulated in a rectangle.

## Declaration

```swift
var rectangle: SymbolVariants { get }
```

## Discussion

Use this property to modify a variant like [fill-swift.property](fill-swift_property.zh-Hans.md) so that it’s also contained in a rectangle:

```swift
Label("Fill Rectangle", systemImage: "plus")
    .symbolVariant(.fill.rectangle)
```



## Modifying a variant

- **circle**: A version of the variant that’s encapsulated in a circle.
- **square**: A version of the variant that’s encapsulated in a square.
- **fill**: A filled version of the variant.
- **slash**: A slashed version of the variant.

