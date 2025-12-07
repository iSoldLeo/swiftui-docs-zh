---
来源： https://developer.apple.com/documentation/SwiftUI/App/body-swift.property
抓取时间： 2025-12-02T17:22:03Z
---

# 正文

**实例属性**

应用程序的内容和行为。

## 声明

```swift
@SceneBuilder @MainActor @preconcurrency var body: Self.Body { get }
```

## 讨论

对于您创建的任何应用程序，请提供一个已计算的 `body` 属性来定义应用程序的场景，这些场景是符合 [Scene](../Scene.zh-Hans.md) 协议的实例。例如，您可以创建一个简单的应用程序，它只有一个包含单一视图的场景：

```swift
@main
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            Text("Hello, world!")
        }
    }
}
```

Swift 会根据`body` 属性提供的场景推断出应用程序的[Body-swift.associatedtype](Body-swift_associatedtype.zh-Hans.md) 关联类型。

## 实现应用程序

- **Body**：代表应用程序内容的场景类型。


---
source: https://developer.apple.com/documentation/SwiftUI/App/body-swift.property
crawled: 2025-12-02T17:22:03Z
---

# body

**Instance Property**

The content and behavior of the app.

## Declaration

```swift
@SceneBuilder @MainActor @preconcurrency var body: Self.Body { get }
```

## Discussion

For any app that you create, provide a computed `body` property that defines your app’s scenes, which are instances that conform to the [Scene](../Scene.zh-Hans.md) protocol. For example, you can create a simple app with a single scene containing a single view:

```swift
@main
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            Text("Hello, world!")
        }
    }
}
```

Swift infers the app’s [Body-swift.associatedtype](Body-swift_associatedtype.zh-Hans.md) associated type based on the scene provided by the `body` property.

## Implementing an app

- **Body**: The type of scene representing the content of the app.

