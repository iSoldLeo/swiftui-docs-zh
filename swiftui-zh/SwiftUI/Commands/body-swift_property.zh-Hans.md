--- 来源：https://developer.apple.com/documentation/SwiftUI/Commands/body-swift.property

抓取时间：2025-12-03T06:22:25Z

---

# body

**实例属性**

命令层级结构的内容。

## 声明

```swift
@CommandsBuilder @MainActor @preconcurrency var body: Self.Body { get }
```

## 讨论

对于您创建的任何命令，请提供一个计算属性 `body`，该属性将场景定义为其他场景的组合。您可以从 SwiftUI 提供的内置命令以及您定义的其他命令来构建命令层级结构。

## 命令的实现

- **Body**：表示此命令层级结构主体的命令类型。


---
source: https://developer.apple.com/documentation/SwiftUI/Commands/body-swift.property
crawled: 2025-12-03T06:22:25Z
---

# body

**Instance Property**

The contents of the command hierarchy.

## Declaration

```swift
@CommandsBuilder @MainActor @preconcurrency var body: Self.Body { get }
```

## Discussion

For any commands that you create, provide a computed `body` property that defines the scene as a composition of other scenes. You can assemble a command hierarchy from built-in commands that SwiftUI provides, as well as other commands that you’ve defined.

## Implementing commands

- **Body**: The type of commands that represents the body of this command hierarchy.

