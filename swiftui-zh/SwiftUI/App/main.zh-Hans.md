---
来源： https://developer.apple.com/documentation/SwiftUI/App/main()
抓取时间： 2025-12-02T17:22:05Z
---

# main()

**类型方法**

初始化并运行应用程序。

## 声明

```swift
@MainActor @preconcurrency static func main()
```

## 讨论

如果您在[App](../App.zh-Hans.md) 构型器的声明前加上 [https://docs.swift.org/swift-book/ReferenceManual/Attributes.html#ID626] 属性，系统会调用构型器的`main()` 方法来启动应用程序。SwiftUI 提供了该方法的默认实现，它以适合平台的方式管理启动过程。

## 运行应用程序

- **init()**：使用您为其内容定义的正文创建应用程序实例。


---
source: https://developer.apple.com/documentation/SwiftUI/App/main()
crawled: 2025-12-02T17:22:05Z
---

# main()

**Type Method**

Initializes and runs the app.

## Declaration

```swift
@MainActor @preconcurrency static func main()
```

## Discussion

If you precede your [App](../App.zh-Hans.md) conformer’s declaration with the [https://docs.swift.org/swift-book/ReferenceManual/Attributes.html#ID626] attribute, the system calls the conformer’s `main()` method to launch the app. SwiftUI provides a default implementation of the method that manages the launch process in a platform-appropriate way.

## Running an app

- **init()**: Creates an instance of the app using the body that you define for its content.

