---
来源： https://developer.apple.com/documentation/SwiftUI/Image/init(_:bundle:)
抓取时间： 2025-12-01T09:18:14Z
---

# init(_:bundle:)

**Initializer**

创建带标签的图片，用作控件的内容。

## 声明

```swift
init(_ name: String, bundle: Bundle? = nil)
```

## 参数

- **name**：要查询的图像资源名称，以及标记图像的本地化密钥。
- **bundle**：用于搜索图像资源和本地化内容的捆绑包。如果 `nil`，SwiftUI 将使用主 `Bundle`。默认为 `nil`。

## 创建图像

- **init(_:variableValue:bundle:)**：创建一个带标签的图像，您可以将其用作控件的内容，并带有一个可变值。
- **init(_:)**：使用图像资源初始化`Image`。


---
source: https://developer.apple.com/documentation/SwiftUI/Image/init(_:bundle:)
crawled: 2025-12-01T09:18:14Z
---

# init(_:bundle:)

**Initializer**

Creates a labeled image that you can use as content for controls.

## Declaration

```swift
init(_ name: String, bundle: Bundle? = nil)
```

## Parameters

- **name**: The name of the image resource to lookup, as well as the localization key with which to label the image.
- **bundle**: The bundle to search for the image resource and localization content. If `nil`, SwiftUI uses the main `Bundle`. Defaults to `nil`.

## Creating an image

- **init(_:variableValue:bundle:)**: Creates a labeled image that you can use as content for controls, with a variable value.
- **init(_:)**: Initialize an `Image` with an image resource.

