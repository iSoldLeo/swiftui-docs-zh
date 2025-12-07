---
源：https://developer.apple.com/documentation/SwiftUI/Image/init(_:variableValue:bundle:)
抓取时间： 2025-12-03T04:28:52Z


# init(_:variableValue:bundle:)

**Initializer**

创建一个带标签的图像，您可以将其用作控件的内容，并带有一个变量值。

## 声明

```swift
init(_ name: String, variableValue: Double?, bundle: Bundle? = nil)
```

## 参数

- **name**：要查询的图像资源名称，以及标记图像的本地化密钥。
- **variableValue**：介于`0.0` 和 `1.0`之间的一个可选值，如果指定了该值，渲染后的图像可以使用它自定义外观。如果符号不支持变量值，该参数将不起作用。
- **bundle**：用于搜索图像资源和本地化内容的捆绑包。如果 `nil`，SwiftUI 将使用主 `Bundle`。默认为 `nil`。

## 讨论

此初始化程序使用指定捆绑包中的符号创建图像。渲染后的符号可能会改变其外观，以表示`variableValue` 中提供的值。



## 创建图像

- **init(_:bundle:)**：创建带标签的图像，用作控件的内容。
- **init(_:)**：使用图像资源初始化`Image`。


---
source: https://developer.apple.com/documentation/SwiftUI/Image/init(_:variableValue:bundle:)
crawled: 2025-12-03T04:28:52Z
---

# init(_:variableValue:bundle:)

**Initializer**

Creates a labeled image that you can use as content for controls, with a variable value.

## Declaration

```swift
init(_ name: String, variableValue: Double?, bundle: Bundle? = nil)
```

## Parameters

- **name**: The name of the image resource to lookup, as well as the localization key with which to label the image.
- **variableValue**: An optional value between `0.0` and `1.0` that the rendered image can use to customize its appearance, if specified. If the symbol doesn’t support variable values, this parameter has no effect.
- **bundle**: The bundle to search for the image resource and localization content. If `nil`, SwiftUI uses the main `Bundle`. Defaults to `nil`.

## Discussion

This initializer creates an image using a using a symbol in the specified bundle. The rendered symbol may alter its appearance to represent the value provided in `variableValue`.



## Creating an image

- **init(_:bundle:)**: Creates a labeled image that you can use as content for controls.
- **init(_:)**: Initialize an `Image` with an image resource.

