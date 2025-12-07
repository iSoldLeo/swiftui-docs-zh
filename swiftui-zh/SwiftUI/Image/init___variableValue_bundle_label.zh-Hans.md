---
来源：https://developer.apple.com/documentation/SwiftUI/Image/init(_:variableValue:bundle:label:)
抓取时间： 2025-12-03T04:28:54Z


# init(_:variableValue:bundle:label:)

**Initializer**

使用指定的标签和变量值创建带标签的图片，用作控件的内容。

### 声明

```swift
init(_ name: String, variableValue: Double?, bundle: Bundle? = nil, label: Text)
```

## 参数

- **name**：要查找的图像资源名称。
- **variableValue**：介于`0.0` 和 `1.0`之间的可选值，如果指定，渲染的图像可以使用该值自定义其外观。如果符号不支持变量值，该参数将不起作用。
- **bundle**：用于搜索图像资源的包。如果 `nil`，SwiftUI 将使用主 `Bundle`。默认为 `nil`。
- **label**：与图像相关联的标签。SwiftUI 使用该标签进行访问。

## 讨论

此初始化程序使用指定捆绑包中的符号创建图像。渲染后的符号可能会改变其外观，以表示`variableValue`中提供的值。



## 创建用作控件的图像

- **init(_:bundle:label:)**：创建一个带标签的图像，您可以用指定的标签将其作为控件的内容。
- **init(_:scale:orientation:label:)**：根据 Core Graphics 图像实例创建标签图像，可用作控件的内容。


---
source: https://developer.apple.com/documentation/SwiftUI/Image/init(_:variableValue:bundle:label:)
crawled: 2025-12-03T04:28:54Z
---

# init(_:variableValue:bundle:label:)

**Initializer**

Creates a labeled image that you can use as content for controls, with the specified label and variable value.

## Declaration

```swift
init(_ name: String, variableValue: Double?, bundle: Bundle? = nil, label: Text)
```

## Parameters

- **name**: The name of the image resource to lookup.
- **variableValue**: An optional value between `0.0` and `1.0` that the rendered image can use to customize its appearance, if specified. If the symbol doesn’t support variable values, this parameter has no effect.
- **bundle**: The bundle to search for the image resource. If `nil`, SwiftUI uses the main `Bundle`. Defaults to `nil`.
- **label**: The label associated with the image. SwiftUI uses the label for accessibility.

## Discussion

This initializer creates an image using a using a symbol in the specified bundle. The rendered symbol may alter its appearance to represent the value provided in `variableValue`.



## Creating an image for use as a control

- **init(_:bundle:label:)**: Creates a labeled image that you can use as content for controls, with the specified label.
- **init(_:scale:orientation:label:)**: Creates a labeled image based on a Core Graphics image instance, usable as content for controls.

