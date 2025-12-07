--- 来源：https://developer.apple.com/documentation/SwiftUI/PresentationSizing/automatic

抓取时间：2025-12-03T06:02:07Z

---

# automatic

**类型属性**

适用于平台的默认显示尺寸。

## 声明

```swift
static var automatic: AutomaticPresentationSizing { get }
```

## 讨论

在 macOS 上，`.automatic` 解析为 `.form.fitted(horizontal: false, vertical: true)`。在所有其他平台（包括 Mac Catalyst）上，它解析为 `.form`。

## 获取内置演示尺寸

- **fitted**：演示尺寸由内容的理想尺寸决定

- **form**：此尺寸适用于表单，宽度略小于`.page`

- **page**：此尺寸大致相当于一张纸的大小，适用于信息性或结构化内容。


---
source: https://developer.apple.com/documentation/SwiftUI/PresentationSizing/automatic
crawled: 2025-12-03T06:02:07Z
---

# automatic

**Type Property**

The default presentation sizing, appropriate for the platform.

## Declaration

```swift
static var automatic: AutomaticPresentationSizing { get }
```

## Discussion

On macOS, `.automatic` resolves to `.form.fitted(horizontal: false, vertical: true)`. On all other platforms, including Mac Catalyst, it resolves to `.form`.



## Getting built-in presentation size

- **fitted**: The presentation sizing is dictated by the ideal size of the content
- **form**: The size is appropriate for forms and slightly less wide than`.page`
- **page**: The size is roughly the size of a page of paper, appropriate for informational or compositional content.

