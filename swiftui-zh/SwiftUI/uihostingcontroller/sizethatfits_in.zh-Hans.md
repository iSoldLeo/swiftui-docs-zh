---
来源： https://developer.apple.com/documentation/SwiftUI/UIHostingController/sizeThatFits(in:)
抓取时间： 2025-12-01T11:48:28Z
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

## 管理大小

- **sizingOptions**：托管控制器如何跟踪其 SwiftUI 内容大小变化的选项。
- **preferredContentSizeDidChange(forChildContentContainer:)**：托管控制器如何跟踪其 SwiftUI 内容大小变化的选项。
- **safeAreaRegions**：该视图控制器添加到其视图中的安全区域。


---
source: https://developer.apple.com/documentation/SwiftUI/UIHostingController/sizeThatFits(in:)
crawled: 2025-12-01T11:48:28Z
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

## Managing the size

- **sizingOptions**: The options for how the hosting controller tracks changes to the size of its SwiftUI content.
- **preferredContentSizeDidChange(forChildContentContainer:)**
- **safeAreaRegions**: The safe area regions that this view controller adds to its view.

