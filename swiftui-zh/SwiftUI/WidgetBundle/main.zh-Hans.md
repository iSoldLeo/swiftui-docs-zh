---

来源：https://developer.apple.com/documentation/SwiftUI/WidgetBundle/main()

抓取时间：2025-11-30T21:33:57Z

---

# main()

**类型方法**

初始化并运行组件包。

## 声明

```swift
@MainActor @preconcurrency static func main()
```

## 概述

由于您在组件包的声明前添加了 [https://docs.swift.org/swift-book/ReferenceManual/Attributes.html#ID626] 属性，系统会调用组件包的 `main()` 方法来启动组件包。SwiftUI 提供了一个默认的 main 方法实现，以平台合适的方式管理启动过程。

## 运行组件包

- **init()**：创建一个组件包，并将组件包的主体作为其内容。


---
source: https://developer.apple.com/documentation/SwiftUI/WidgetBundle/main()
crawled: 2025-11-30T21:33:57Z
---

# main()

**Type Method**

Initializes and runs the widget bundle.

## Declaration

```swift
@MainActor @preconcurrency static func main()
```

## Overview

Because you precede your [WidgetBundle](../WidgetBundle.zh-Hans.md) conformer’s declaration with the [https://docs.swift.org/swift-book/ReferenceManual/Attributes.html#ID626] attribute, the system calls your widget bundle’s `main()` method to launch the widget bundle. SwiftUI provides a default implementation of the method that manages the launch process in a platform-appropriate way.

## Running a widget bundle

- **init()**: Creates a widget bundle using the bundle’s body as its content.

