---
来源： https://developer.apple.com/documentation/SwiftUI/WindowResizability/contentSize
抓取时间： 2025-12-03T05:32:06Z
---

# contentSize

**类型属性**

从窗口内容中导出的窗口大小可变性。

## 声明

```swift
static var contentSize: WindowResizability { get set }
```

## 讨论

使用这种可调整大小功能的窗口有

- 最小尺寸与窗口内容的最小尺寸一致。
- 与窗口内容最大尺寸相匹配的最大尺寸。

## 获取可调整大小

- **automatic**：自动调整窗口大小。
- **contentMinSize**：部分源自窗口内容的窗口可调整性。


---
source: https://developer.apple.com/documentation/SwiftUI/WindowResizability/contentSize
crawled: 2025-12-03T05:32:06Z
---

# contentSize

**Type Property**

A window resizability that’s derived from the window’s content.

## Declaration

```swift
static var contentSize: WindowResizability { get set }
```

## Discussion

Windows that use this resizability have:

- A minimum size that matches the minimum size of the window’s content.
- A maximum size that matches the maximum size of the window’s content.

## Getting the resizability

- **automatic**: The automatic window resizability.
- **contentMinSize**: A window resizability that’s partially derived from the window’s content.

