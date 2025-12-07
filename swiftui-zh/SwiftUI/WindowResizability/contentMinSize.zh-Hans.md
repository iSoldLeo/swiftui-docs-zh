---
来源： https://developer.apple.com/documentation/SwiftUI/WindowResizability/contentMinSize
抓取时间： 2025-12-03T05:32:05Z
---

# contentMinSize

**类型属性**

窗口大小可调整性，部分源自窗口内容。

## 声明

```swift
static var contentMinSize: WindowResizability { get set }
```

## 讨论

使用这种可调整大小功能的窗口有

- 最小尺寸与窗口内容的最小尺寸一致。
- 无最大尺寸。

## 获取可调整大小

- **automatic**：自动调整窗口大小。
- **contentSize**：根据窗口内容调整窗口大小。


---
source: https://developer.apple.com/documentation/SwiftUI/WindowResizability/contentMinSize
crawled: 2025-12-03T05:32:05Z
---

# contentMinSize

**Type Property**

A window resizability that’s partially derived from the window’s content.

## Declaration

```swift
static var contentMinSize: WindowResizability { get set }
```

## Discussion

Windows that use this resizability have:

- A minimum size that matches the minimum size of the window’s content.
- No maximum size.

## Getting the resizability

- **automatic**: The automatic window resizability.
- **contentSize**: A window resizability that’s derived from the window’s content.

