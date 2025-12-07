---
来源：https://developer.apple.com/documentation/SwiftUI/Image/init(systemName:variableValue:)
抓取时间：2025-12-03T04:28:59Z


# init(systemName:variableValue:)

**Initializer**

创建带有变量值的系统符号图像。

## 声明

```swift
init(systemName: String, variableValue: Double?)
```

## 参数

- **systemName**：系统符号映像的名称。使用 SF Symbols 应用程序查找系统符号映像的名称。
- **variableValue**：介于`0.0` 和 `1.0`之间的可选值，如果指定，渲染图像可使用该值自定义其外观。如果符号不支持变量值，该参数将不起作用。请使用 SF Symbols 应用程序查找哪些符号支持变量值。

## 讨论

此初始化程序使用系统提供的符号创建图像。渲染后的符号可能会改变其外观，以表示`variableValue` 中提供的值。请使用 [https://developer.apple.com/design/resources/#sf-symbols]（4.0 或更高版本）查找支持变量值的系统符号及其相应名称。

下面的示例显示了创建具有不同值的`"chart.bar.fill"` 符号的效果。

```swift
HStack{
    Image(systemName: "chart.bar.fill", variableValue: 0.3)
    Image(systemName: "chart.bar.fill", variableValue: 0.6)
    Image(systemName: "chart.bar.fill", variableValue: 1.0)
}
.font(.system(.largeTitle))
```



要从应用程序的资产目录中创建自定义符号图像，请使用 [init(_:variableValue:bundle:)](init___variableValue_bundle.zh-Hans.md) 代替。

## 创建系统符号图像

- **init(systemName:)**：创建系统符号映像。


---
source: https://developer.apple.com/documentation/SwiftUI/Image/init(systemName:variableValue:)
crawled: 2025-12-03T04:28:59Z
---

# init(systemName:variableValue:)

**Initializer**

Creates a system symbol image with a variable value.

## Declaration

```swift
init(systemName: String, variableValue: Double?)
```

## Parameters

- **systemName**: The name of the system symbol image. Use the SF Symbols app to look up the names of system symbol images.
- **variableValue**: An optional value between `0.0` and `1.0` that the rendered image can use to customize its appearance, if specified. If the symbol doesn’t support variable values, this parameter has no effect. Use the SF Symbols app to look up which symbols support variable values.

## Discussion

This initializer creates an image using a system-provided symbol. The rendered symbol may alter its appearance to represent the value provided in `variableValue`. Use [https://developer.apple.com/design/resources/#sf-symbols] (version 4.0 or later) to find system symbols that support variable values and their corresponding names.

The following example shows the effect of creating the `"chart.bar.fill"` symbol with different values.

```swift
HStack{
    Image(systemName: "chart.bar.fill", variableValue: 0.3)
    Image(systemName: "chart.bar.fill", variableValue: 0.6)
    Image(systemName: "chart.bar.fill", variableValue: 1.0)
}
.font(.system(.largeTitle))
```



To create a custom symbol image from your app’s asset catalog, use [init(_:variableValue:bundle:)](init___variableValue_bundle.zh-Hans.md) instead.

## Creating a system symbol image

- **init(systemName:)**: Creates a system symbol image.

