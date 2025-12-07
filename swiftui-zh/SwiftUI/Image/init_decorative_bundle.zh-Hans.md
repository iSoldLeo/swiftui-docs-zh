---
来源：https://developer.apple.com/documentation/SwiftUI/Image/init(decorative:bundle:)
抓取时间： 2025-12-03T04:28:56Z
---

# init(decorative:bundle:)

**Initializer**

创建一个无标记的装饰图像。

## 声明

```swift
init(decorative name: String, bundle: Bundle? = nil)
```

## 参数

- **name**：要查找的图像资源名称
- **bundle**：要搜索图像资源的包。如果 `nil`，SwiftUI 将使用主 `Bundle`。默认为 `nil`。

## 讨论

为便于访问，SwiftUI 会忽略此图像。

## 创建装饰用图像

- **init(decorative:variableValue:bundle:)**：创建一个无标记的装饰性图像，其值可变。
- **init(decorative:scale:orientation:)**：根据 Core Graphics 图像实例创建无标记的装饰图像。


---
source: https://developer.apple.com/documentation/SwiftUI/Image/init(decorative:bundle:)
crawled: 2025-12-03T04:28:56Z
---

# init(decorative:bundle:)

**Initializer**

Creates an unlabeled, decorative image.

## Declaration

```swift
init(decorative name: String, bundle: Bundle? = nil)
```

## Parameters

- **name**: The name of the image resource to lookup
- **bundle**: The bundle to search for the image resource. If `nil`, SwiftUI uses the main `Bundle`. Defaults to `nil`.

## Discussion

SwiftUI ignores this image for accessibility purposes.

## Creating an image for decorative use

- **init(decorative:variableValue:bundle:)**: Creates an unlabeled, decorative image, with a variable value.
- **init(decorative:scale:orientation:)**: Creates an unlabeled, decorative image based on a Core Graphics image instance.

