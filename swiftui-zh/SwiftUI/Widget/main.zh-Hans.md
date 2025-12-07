---
来源： https://developer.apple.com/documentation/SwiftUI/Widget/main()
抓取时间： 2025-12-03T06:05:41Z
---

# main()

**类型方法**

初始化并运行 widget。

## 声明

```swift
@MainActor @preconcurrency static func main()
```

## 概览

由于您在[Widget](../Widget.zh-Hans.md) 符合者声明之前使用了 [https://docs.swift.org/swift-book/ReferenceManual/Attributes.html#ID626] 属性，系统会调用您的 widget 的`main()` 方法来启动 widget。SwiftUI 提供了该方法的默认实现，它以适合平台的方式管理启动过程。

## 运行部件

- **init()**：创建一个以 `body` 为内容的 widget。


---
source: https://developer.apple.com/documentation/SwiftUI/Widget/main()
crawled: 2025-12-03T06:05:41Z
---

# main()

**Type Method**

Initializes and runs the widget.

## Declaration

```swift
@MainActor @preconcurrency static func main()
```

## Overview

Because you precede your [Widget](../Widget.zh-Hans.md) conformer’s declaration with the [https://docs.swift.org/swift-book/ReferenceManual/Attributes.html#ID626] attribute, the system calls your widget’s `main()` method to launch the widget. SwiftUI provides a default implementation of the method that manages the launch process in a platform-appropriate way.

## Running a widget

- **init()**: Creates a widget using `body` as its content.

