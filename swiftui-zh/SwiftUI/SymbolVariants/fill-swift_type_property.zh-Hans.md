--- 来源：https://developer.apple.com/documentation/SwiftUI/SymbolVariants/fill-swift.type.property

抓取时间：2025-12-03T06:21:23Z

---

# fill

**类型属性**

用于填充符号的变体。

## 声明

```swift
static let fill: SymbolVariants
```

## 讨论

对于具有填充变体的符号，请使用此变体并调用 [symbolVariant(_:)](../View/symbolVariant.zh-Hans.md) 修饰符来绘制填充符号：

```swift
VStack(spacing: 20) {
    HStack(spacing: 20) {
        Image(systemName: "flag")
        Image(systemName: "heart")
        Image(systemName: "bolt")
        Image(systemName: "star")
    }
    HStack(spacing: 20) {
        Image(systemName: "flag")
        Image(systemName: "heart")
        Image(systemName: "bolt")
        Image(systemName: "star")
    }
    .symbolVariant(.fill)
}
```

## 获取符号变体

- **none**：符号没有变体。

- **circle**：将符号封装在圆圈中的变体。

- **square**：将符号封装在正方形内的变体。

- **rectangle**：将符号封装在矩形内的变体。

- **slash**：在符号上画一条斜线的变体。


---
source: https://developer.apple.com/documentation/SwiftUI/SymbolVariants/fill-swift.type.property
crawled: 2025-12-03T06:21:23Z
---

# fill

**Type Property**

A variant that fills the symbol.

## Declaration

```swift
static let fill: SymbolVariants
```

## Discussion

Use this variant with a call to the [symbolVariant(_:)](../View/symbolVariant.zh-Hans.md) modifier to draw filled symbols, for those symbols that have a filled variant:

```swift
VStack(spacing: 20) {
    HStack(spacing: 20) {
        Image(systemName: "flag")
        Image(systemName: "heart")
        Image(systemName: "bolt")
        Image(systemName: "star")
    }
    HStack(spacing: 20) {
        Image(systemName: "flag")
        Image(systemName: "heart")
        Image(systemName: "bolt")
        Image(systemName: "star")
    }
    .symbolVariant(.fill)
}
```



## Getting symbol variants

- **none**: No variant for a symbol.
- **circle**: A variant that encapsulates the symbol in a circle.
- **square**: A variant that encapsulates the symbol in a square.
- **rectangle**: A variant that encapsulates the symbol in a rectangle.
- **slash**: A variant that draws a slash through the symbol.

