--- 来源：https://developer.apple.com/documentation/swiftui/scenebuilder
抓取时间：2025-12-04T13:47:25Z

---

# SceneBuilder

**Structure**

一个用于将多个场景组合成一个复合场景的结果构建器。

## 声明

```swift
@resultBuilder struct SceneBuilder
```

## 构建内容

- **buildBlock(_:)**：将作为子场景编写的单个场景原封不动地传递过去。

- **buildExpression(_:)**：在构建器内部构建表达式。

- **buildLimitedAvailability(_:)**：处理场景内容，以检查是否存在条件编译器控制语句执行的可用性检查。

- **buildOptional(_:)**：为多语句闭包中的条件语句生成一个可选场景，该场景仅在条件为真时可见。

## 创建场景

- **Scene**：应用程序用户界面的一部分，其生命周期由系统管理。


---
source: https://developer.apple.com/documentation/swiftui/scenebuilder
crawled: 2025-12-04T13:47:25Z
---

# SceneBuilder

**Structure**

A result builder for composing a collection of scenes into a single composite scene.

## Declaration

```swift
@resultBuilder struct SceneBuilder
```

## Building content

- **buildBlock(_:)**: Passes a single scene written as a child scene through unmodified.
- **buildExpression(_:)**: Builds an expression within the builder.
- **buildLimitedAvailability(_:)**: Processes scene content for a conditional compiler-control statement that performs an availability check.
- **buildOptional(_:)**: Produces an optional scene for conditional statements in multi-statement closures that’s only visible when the condition evaluates to true.

## Creating scenes

- **Scene**: A part of an app’s user interface with a life cycle managed by the system.

