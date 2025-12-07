---
来源： https://developer.apple.com/documentation/SwiftUI/NSHostingController/sizeThatFits(in:)
抓取时间： 2025-12-01T11:39:45Z
---

# sizeThatFits(in:)

**实例方法**

计算并返回最适合当前视图的尺寸。

## 声明

```swift
@MainActor @preconcurrency func sizeThatFits(in size: CGSize) -> CGSize
```

## 参数

- **size**：建议的视图新尺寸。

## 返回值

最适合根视图及其内容的大小。

## 配置控制器

- **preferredContentSize**
- **sizingOptions**：托管控制器视图如何根据其 SwiftUI 内容的大小创建和更新约束的选项。
- **safeAreaRegions**：该视图控制器添加到其视图的安全区域。
- **sceneBridgingOptions**：窗口的哪些方面将由此控制器的托管视图管理的选项。


---
source: https://developer.apple.com/documentation/SwiftUI/NSHostingController/sizeThatFits(in:)
crawled: 2025-12-01T11:39:45Z
---

# sizeThatFits(in:)

**Instance Method**

Calculates and returns the most appropriate size for the current view.

## Declaration

```swift
@MainActor @preconcurrency func sizeThatFits(in size: CGSize) -> CGSize
```

## Parameters

- **size**: The proposed new size for the view.

## Return Value

The size that offers the best fit for the root view and its contents.

## Configuring the controller

- **preferredContentSize**
- **sizingOptions**: The options for how the hosting controller’s view creates and updates constraints based on the size of its SwiftUI content.
- **safeAreaRegions**: The safe area regions that this view controller adds to its view.
- **sceneBridgingOptions**: The options for which aspects of the window will be managed by this controller’s hosting view.

