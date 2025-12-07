--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/body-swift.property

抓取时间：2025-12-03T05:31:01Z

---

# body

**实例属性**

场景的内容和行为。

## 声明

```swift
@SceneBuilder @MainActor @preconcurrency var body: Self.Body { get }
```

## 讨论

对于您创建的任何场景，请提供一个计算属性 `body`，该属性将场景定义为其他场景的组合。您可以从 SwiftUI 提供的内置场景以及您定义的其他场景来组装场景。

Swift 会根据 `body` 属性的内容推断场景的 [Body-swift.associatedtype](Body-swift_associatedtype.zh-Hans.md) 关联类型。

## 创建场景

- **Body**：代表此场景主体部分的场景类型。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/body-swift.property
crawled: 2025-12-03T05:31:01Z
---

# body

**Instance Property**

The content and behavior of the scene.

## Declaration

```swift
@SceneBuilder @MainActor @preconcurrency var body: Self.Body { get }
```

## Discussion

For any scene that you create, provide a computed `body` property that defines the scene as a composition of other scenes. You can assemble a scene from built-in scenes that SwiftUI provides, as well as other scenes that you’ve defined.

Swift infers the scene’s [Body-swift.associatedtype](Body-swift_associatedtype.zh-Hans.md) associated type based on the contents of the `body` property.

## Creating a scene

- **Body**: The type of scene that represents the body of this scene.

