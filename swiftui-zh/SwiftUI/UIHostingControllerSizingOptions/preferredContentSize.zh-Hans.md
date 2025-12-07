---
来源： https://developer.apple.com/documentation/SwiftUI/UIHostingControllerSizingOptions/preferredContentSize
抓取时间： 2025-12-03T07:00:22Z
---

# preferredContentSize

**类型属性**

托管控制器在首选内容大小中跟踪其内容的理想大小。

## 声明

```swift
static let preferredContentSize: UIHostingControllerSizingOptions
```

## 讨论

在使用托管控制器和容器视图控制器时，如果需要了解托管控制器理想尺寸的最新情况，请使用此选项。



## 获取大小选项

- **intrinsicContentSize**：托管控制器的视图在其理想尺寸发生变化时，其内在内容尺寸会自动失效。


---
source: https://developer.apple.com/documentation/SwiftUI/UIHostingControllerSizingOptions/preferredContentSize
crawled: 2025-12-03T07:00:22Z
---

# preferredContentSize

**Type Property**

The hosting controller tracks its content’s ideal size in its preferred content size.

## Declaration

```swift
static let preferredContentSize: UIHostingControllerSizingOptions
```

## Discussion

Use this option when using a hosting controller with a container view controller that requires up-to-date knowledge of the hosting controller’s ideal size.



## Getting sizing options

- **intrinsicContentSize**: The hosting controller’s view automatically invalidate its intrinsic content size when its ideal size changes.

