--- 来源：https://developer.apple.com/documentation/SwiftUI/SymbolVariants/square-swift.type.property

抓取时间：2025-12-03T06:21:21Z

---

# square

**类型属性**

将符号封装在正方形中的变体。

## 声明

```swift
static let square: SymbolVariants
```

## 讨论

对于具有正方形变体的符号，请使用此变体并调用 [symbolVariant(_:)](../View/symbolVariant.zh-Hans.md) 修饰符，以在正方形中绘制符号：

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
    .symbolVariant(.square)
}
```

## 获取符号变体

- **none**：符号没有变体。

- **circle**：将符号封装在圆形中的变体。

- **rectangle**：将符号封装在矩形框内的变体。

- **fill**：填充符号的变体。

- **slash**：在符号上绘制斜杠的变体。


---
source: https://developer.apple.com/documentation/SwiftUI/SymbolVariants/square-swift.type.property
crawled: 2025-12-03T06:21:21Z
---

# square

**Type Property**

A variant that encapsulates the symbol in a square.

## Declaration

```swift
static let square: SymbolVariants
```

## Discussion

Use this variant with a call to the [symbolVariant(_:)](../View/symbolVariant.zh-Hans.md) modifier to draw symbols in a square, for those symbols that have a square variant:

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
    .symbolVariant(.square)
}
```



## Getting symbol variants

- **none**: No variant for a symbol.
- **circle**: A variant that encapsulates the symbol in a circle.
- **rectangle**: A variant that encapsulates the symbol in a rectangle.
- **fill**: A variant that fills the symbol.
- **slash**: A variant that draws a slash through the symbol.

