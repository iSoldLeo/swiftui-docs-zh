---
source: https://developer.apple.com/documentation/SwiftUI/Image/init(decorative:variableValue:bundle:)
抓取时间：2025-12-01T09:18:20Z


# init(decorative:variableValue:bundle:)

**Initializer**

使用变量值创建一个无标记的装饰图像。

### 声明

```swift
init(decorative name: String, variableValue: Double?, bundle: Bundle? = nil)
```

## 参数

- **name**：要查找的图像资源名称。
- **variableValue**：介于`0.0` 和 `1.0`之间的可选值，如果指定，渲染的图像可以使用该值自定义其外观。如果符号不支持变量值，该参数将不起作用。
- **bundle**：用于搜索图像资源的捆绑包。如果 `nil`，SwiftUI 将使用主 `Bundle`。默认为 `nil`。

## 讨论

此初始化程序使用指定捆绑包中的符号创建图像。渲染后的符号可能会改变其外观，以表示`variableValue` 中提供的值。



为便于访问，SwiftUI 将忽略此图像。

## 创建装饰用图像

- **init(decorative:bundle:)**：创建一个无标记的装饰性图像。
- **init(decorative:scale:orientation:)**：根据 Core Graphics 图像实例创建未标记的装饰图像。


---
source: https://developer.apple.com/documentation/SwiftUI/Image/init(decorative:variableValue:bundle:)
crawled: 2025-12-01T09:18:20Z
---

# init(decorative:variableValue:bundle:)

**Initializer**

Creates an unlabeled, decorative image, with a variable value.

## Declaration

```swift
init(decorative name: String, variableValue: Double?, bundle: Bundle? = nil)
```

## Parameters

- **name**: The name of the image resource to lookup.
- **variableValue**: An optional value between `0.0` and `1.0` that the rendered image can use to customize its appearance, if specified. If the symbol doesn’t support variable values, this parameter has no effect.
- **bundle**: The bundle to search for the image resource. If `nil`, SwiftUI uses the main `Bundle`. Defaults to `nil`.

## Discussion

This initializer creates an image using a using a symbol in the specified bundle. The rendered symbol may alter its appearance to represent the value provided in `variableValue`.



SwiftUI ignores this image for accessibility purposes.

## Creating an image for decorative use

- **init(decorative:bundle:)**: Creates an unlabeled, decorative image.
- **init(decorative:scale:orientation:)**: Creates an unlabeled, decorative image based on a Core Graphics image instance.

