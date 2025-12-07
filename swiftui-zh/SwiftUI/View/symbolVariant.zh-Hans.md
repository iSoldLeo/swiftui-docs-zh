--- 来源：https://developer.apple.com/documentation/SwiftUI/View/symbolVariant(_:)

抓取时间：2025-12-02T17:04:48Z

---

# symbolVariant(_:)

**实例方法**

使视图中的符号显示特定的变体。

## 声明

```swift
nonisolated func symbolVariant(_ variant: SymbolVariants) -> some View

```

## 参数

- **variant**：用于符号的变体。使用 [SymbolVariants](../SymbolVariants.zh-Hans.md) 中的值。

## 返回值

一个将指定的符号变体应用于自身及其子视图的视图。

## 讨论

如果您希望应用程序用户界面中某个部分的所有 [doc://com.apple.documentation/design/Human-Interface-Guidelines/sf-symbols] 使用相同的变体，请使用 `symbolVariant(_:)` 修饰符，并赋予其 [SymbolVariants](../SymbolVariants.zh-Hans.md) 值，例如 [fill-swift.type.property](../SymbolVariants/fill-swift_type_property.zh-Hans.md)：

```swift
VStack(spacing: 20) {
    HStack(spacing: 20) {
        Image(systemName: "person")
        Image(systemName: "folder")
        Image(systemName: "gearshape")
        Image(systemName: "list.bullet")
    }

    HStack(spacing: 20) {
        Image(systemName: "person")
        Image(systemName: "folder")
        Image(systemName: "gearshape")
        Image(systemName: "list.bullet")
    }
    .symbolVariant(.fill) // Shows filled variants, when available.
}
```

未指定变体的符号将不受影响。在上面的示例中，`list.bullet` 符号没有填充变体，因此 `symbolVariant(_:)` 修饰符无效。

如果多次应用修饰符，其效果会累加。或者，您可以在一次调用中应用多个变体：

```swift
Label("Airplane", systemImage: "airplane.circle.fill")

Label("Airplane", systemImage: "airplane")
    .symbolVariant(.circle)
    .symbolVariant(.fill)

Label("Airplane", systemImage: "airplane")
    .symbolVariant(.circle.fill)
```

以上代码中的所有标签都会产生相同的输出：

您可以按任意顺序应用所有这些变体，但如果您应用多个形状变体，则距离符号最近的变体优先。例如，下图使用了 [square-swift.type.property](../SymbolVariants/square-swift_type_property.zh-Hans.md) 形状：

```swift
Image(systemName: "arrow.left")
    .symbolVariant(.square) // This shape takes precedence.
    .symbolVariant(.circle)
    .symbolVariant(.fill)
```

要使符号忽略当前环境中的变体，请使用 [environment(_:_:)](environment.zh-Hans.md) 修饰符将 [symbolVariants](../EnvironmentValues/symbolVariants.zh-Hans.md) 环境值直接设置为 [none](../SymbolVariants/none.zh-Hans.md)。

## 设置符号变体

- **symbolVariants**：要在此环境中使用的符号变体。

- **SymbolVariants**：符号的变体。


---
source: https://developer.apple.com/documentation/SwiftUI/View/symbolVariant(_:)
crawled: 2025-12-02T17:04:48Z
---

# symbolVariant(_:)

**Instance Method**

Makes symbols within the view show a particular variant.

## Declaration

```swift
nonisolated func symbolVariant(_ variant: SymbolVariants) -> some View

```

## Parameters

- **variant**: The variant to use for symbols. Use the values in [SymbolVariants](../SymbolVariants.zh-Hans.md).

## Return Value

A view that applies the specified symbol variant or variants to itself and its child views.

## Discussion

When you want all the [doc://com.apple.documentation/design/Human-Interface-Guidelines/sf-symbols] in a part of your app’s user interface to use the same variant, use the `symbolVariant(_:)` modifier with a [SymbolVariants](../SymbolVariants.zh-Hans.md) value, like [fill-swift.type.property](../SymbolVariants/fill-swift_type_property.zh-Hans.md):

```swift
VStack(spacing: 20) {
    HStack(spacing: 20) {
        Image(systemName: "person")
        Image(systemName: "folder")
        Image(systemName: "gearshape")
        Image(systemName: "list.bullet")
    }

    HStack(spacing: 20) {
        Image(systemName: "person")
        Image(systemName: "folder")
        Image(systemName: "gearshape")
        Image(systemName: "list.bullet")
    }
    .symbolVariant(.fill) // Shows filled variants, when available.
}
```

A symbol that doesn’t have the specified variant remains unaffected. In the example above, the `list.bullet` symbol doesn’t have a filled variant, so the `symbolVariant(_:)` modifer has no effect.



If you apply the modifier more than once, its effects accumulate. Alternatively, you can apply multiple variants in one call:

```swift
Label("Airplane", systemImage: "airplane.circle.fill")

Label("Airplane", systemImage: "airplane")
    .symbolVariant(.circle)
    .symbolVariant(.fill)

Label("Airplane", systemImage: "airplane")
    .symbolVariant(.circle.fill)
```

All of the labels in the code above produce the same output:



You can apply all these variants in any order, but if you apply more than one shape variant, the one closest to the symbol takes precedence. For example, the following image uses the [square-swift.type.property](../SymbolVariants/square-swift_type_property.zh-Hans.md) shape:

```swift
Image(systemName: "arrow.left")
    .symbolVariant(.square) // This shape takes precedence.
    .symbolVariant(.circle)
    .symbolVariant(.fill)
```



To cause a symbol to ignore the variants currently in the environment, directly set the [symbolVariants](../EnvironmentValues/symbolVariants.zh-Hans.md) environment value to [none](../SymbolVariants/none.zh-Hans.md) using the [environment(_:_:)](environment.zh-Hans.md) modifer.

## Setting a symbol variant

- **symbolVariants**: The symbol variant to use in this environment.
- **SymbolVariants**: A variant of a symbol.

