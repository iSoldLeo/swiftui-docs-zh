---
来源：https://developer.apple.com/documentation/SwiftUI/Image/init(_:bundle:label:)
抓取时间： 2025-12-01T09:18:16Z
---

# init(_:bundle:label:)

**Initializer**

创建带标签的图片，您可以将其用作控件的内容，并带有指定的标签。

### 声明

```swift
init(_ name: String, bundle: Bundle? = nil, label: Text)
```

## 参数

- **name**：要查找的图像资源名称
- **bundle**：要搜索图像资源的包。如果 `nil`，SwiftUI 将使用主 `Bundle`。默认为 `nil`。
- **label**：与图像相关联的标签。SwiftUI 使用该标签进行访问。

## 创建用作控件的图像

- **init(_:variableValue:bundle:label:)**：创建一个带标签的图像，您可以使用指定的标签和变量值将其作为控件的内容。
- **init(_:scale:orientation:label:)**：根据 Core Graphics 图像实例创建带标记的图像，可用作控件的内容。


---
source: https://developer.apple.com/documentation/SwiftUI/Image/init(_:bundle:label:)
crawled: 2025-12-01T09:18:16Z
---

# init(_:bundle:label:)

**Initializer**

Creates a labeled image that you can use as content for controls, with the specified label.

## Declaration

```swift
init(_ name: String, bundle: Bundle? = nil, label: Text)
```

## Parameters

- **name**: The name of the image resource to lookup
- **bundle**: The bundle to search for the image resource. If `nil`, SwiftUI uses the main `Bundle`. Defaults to `nil`.
- **label**: The label associated with the image. SwiftUI uses the label for accessibility.

## Creating an image for use as a control

- **init(_:variableValue:bundle:label:)**: Creates a labeled image that you can use as content for controls, with the specified label and variable value.
- **init(_:scale:orientation:label:)**: Creates a labeled image based on a Core Graphics image instance, usable as content for controls.

