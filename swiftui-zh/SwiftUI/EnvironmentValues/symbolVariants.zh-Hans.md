---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/symbolVariants
抓取时间： 2025-12-02T17:35:51Z
---

# symbolVariants

**实例属性**

在此环境中使用的符号变量。

## 声明

```swift
var symbolVariants: SymbolVariants { get set }
```

## 讨论

您可以使用[symbolVariant(_:)](../View/symbolVariant.zh-Hans.md) 视图修饰符间接设置该环境值。不过，您可以使用 [environment(_:_:)](../View/environment.zh-Hans.md) 修饰符直接访问该环境变量。当您想使用 [none](../SymbolVariants/none.zh-Hans.md) 变量来忽略环境中已经存在的值时，可以这样做：

```swift
HStack {
    Image(systemName: "heart")
    Image(systemName: "heart")
        .environment(\.symbolVariants, .none)
}
.symbolVariant(.fill)
```



## 设置符号变量

- **symbolVariant(_:)**：使视图中的符号显示特定变体。
- **SymbolVariants**：符号的变体。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/symbolVariants
crawled: 2025-12-02T17:35:51Z
---

# symbolVariants

**Instance Property**

The symbol variant to use in this environment.

## Declaration

```swift
var symbolVariants: SymbolVariants { get set }
```

## Discussion

You set this environment value indirectly by using the [symbolVariant(_:)](../View/symbolVariant.zh-Hans.md) view modifier. However, you access the environment variable directly using the [environment(_:_:)](../View/environment.zh-Hans.md) modifier. Do this when you want to use the [none](../SymbolVariants/none.zh-Hans.md) variant to ignore the value that’s already in the environment:

```swift
HStack {
    Image(systemName: "heart")
    Image(systemName: "heart")
        .environment(\.symbolVariants, .none)
}
.symbolVariant(.fill)
```



## Setting a symbol variant

- **symbolVariant(_:)**: Makes symbols within the view show a particular variant.
- **SymbolVariants**: A variant of a symbol.

