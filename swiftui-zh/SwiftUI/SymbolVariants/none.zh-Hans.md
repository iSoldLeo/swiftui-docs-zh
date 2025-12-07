--- 来源：https://developer.apple.com/documentation/SwiftUI/SymbolVariants/none
抓取时间：2025-12-03T06:21:20Z

---

# none

**类型属性**

符号没有变体。

## 声明

```swift
static let none: SymbolVariants
```

## 讨论

将此变体与 [symbolVariant(_:)](../View/symbolVariant.zh-Hans.md) 修饰符一起使用无效。要显示一个忽略当前变体的符号，请直接使用 [environment(_:_:)](../View/environment.zh-Hans.md) 修饰符将 [symbolVariants](../EnvironmentValues/symbolVariants.zh-Hans.md) 环境值设置为 `none`：

```swift
HStack {
    Image(systemName: "heart")
    Image(systemName: "heart")
        .environment(\.symbolVariants, .none)
}
.symbolVariant(.fill)
```

## 获取符号变体

- **circle**：将符号封装在圆圈中的变体。

- **square**：将符号封装在正方形中的变体。

- **rectangle**：将符号封装在矩形中的变体。

- **fill**：填充符号的变体。

- **slash**：在符号上绘制斜线的变体。


---
source: https://developer.apple.com/documentation/SwiftUI/SymbolVariants/none
crawled: 2025-12-03T06:21:20Z
---

# none

**Type Property**

No variant for a symbol.

## Declaration

```swift
static let none: SymbolVariants
```

## Discussion

Using this variant with the [symbolVariant(_:)](../View/symbolVariant.zh-Hans.md) modifier doesn’t have any effect. Instead, to show a symbol that ignores the current variant, directly set the [symbolVariants](../EnvironmentValues/symbolVariants.zh-Hans.md) environment value to `none` using the [environment(_:_:)](../View/environment.zh-Hans.md) modifer:

```swift
HStack {
    Image(systemName: "heart")
    Image(systemName: "heart")
        .environment(\.symbolVariants, .none)
}
.symbolVariant(.fill)
```



## Getting symbol variants

- **circle**: A variant that encapsulates the symbol in a circle.
- **square**: A variant that encapsulates the symbol in a square.
- **rectangle**: A variant that encapsulates the symbol in a rectangle.
- **fill**: A variant that fills the symbol.
- **slash**: A variant that draws a slash through the symbol.

