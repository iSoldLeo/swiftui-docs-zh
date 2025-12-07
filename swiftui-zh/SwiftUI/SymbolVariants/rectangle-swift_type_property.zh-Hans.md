--- 来源：https://developer.apple.com/documentation/SwiftUI/SymbolVariants/rectangle-swift.type.property

抓取时间：2025-12-03T06:21:22Z

---

# rectangle

**类型属性**

一个将符号封装在矩形中的变体。

## 声明

```swift
static let rectangle: SymbolVariants
```

## 讨论

对于具有矩形变体的符号，可以使用此变体并调用 [symbolVariant(_:)](../View/symbolVariant.zh-Hans.md) 修饰符，以矩形方式绘制符号：

```swift
VStack(spacing: 20) {
    HStack(spacing: 20) {
        Image(systemName: "plus")
        Image(systemName: "minus")
        Image(systemName: "xmark")
        Image(systemName: "checkmark")
    }
    HStack(spacing: 20) {
        Image(systemName: "plus")
        Image(systemName: "minus")
        Image(systemName: "xmark")
        Image(systemName: "checkmark")
    }
    .symbolVariant(.rectangle)
}
```

## 获取符号变体

- **none**：符号没有变体。

- **circle**：一个将符号封装在圆形中的变体。

- **square**：将符号封装在正方形内的变体。

- **fill**：填充符号的变体。

- **slash**：在符号上绘制斜线的变体。


---
source: https://developer.apple.com/documentation/SwiftUI/SymbolVariants/rectangle-swift.type.property
crawled: 2025-12-03T06:21:22Z
---

# rectangle

**Type Property**

A variant that encapsulates the symbol in a rectangle.

## Declaration

```swift
static let rectangle: SymbolVariants
```

## Discussion

Use this variant with a call to the [symbolVariant(_:)](../View/symbolVariant.zh-Hans.md) modifier to draw symbols in a rectangle, for those symbols that have a rectangle variant:

```swift
VStack(spacing: 20) {
    HStack(spacing: 20) {
        Image(systemName: "plus")
        Image(systemName: "minus")
        Image(systemName: "xmark")
        Image(systemName: "checkmark")
    }
    HStack(spacing: 20) {
        Image(systemName: "plus")
        Image(systemName: "minus")
        Image(systemName: "xmark")
        Image(systemName: "checkmark")
    }
    .symbolVariant(.rectangle)
}
```



## Getting symbol variants

- **none**: No variant for a symbol.
- **circle**: A variant that encapsulates the symbol in a circle.
- **square**: A variant that encapsulates the symbol in a square.
- **fill**: A variant that fills the symbol.
- **slash**: A variant that draws a slash through the symbol.

