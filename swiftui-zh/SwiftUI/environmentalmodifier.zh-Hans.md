--- 来源：https://developer.apple.com/documentation/swiftui/environmentalmodifier
抓取时间：2025-12-02T17:47:20Z

---

# 环境修饰符

**Protocol**

使用前必须解析为环境中的具体修饰符的修饰符。

## 声明

```swift
protocol EnvironmentalModifier : ViewModifier where Self.Body == Never
```

## 解析修饰符

- **resolve(in:)**：解析为给定 `environment` 中的具体修饰符。

- **ResolvedModifier**：解析后要使用的修饰符类型。

## 修改视图

- **配置视图**：通过应用视图修饰符来调整视图的特性。

- **减少视图修饰符维护**：将经常重复使用的视图修饰符打包成一个自定义视图修饰符。

- **modifier(_:)**：将修饰符应用于视图并返回一个新视图。

- **ViewModifier**：应用于视图或其他视图修饰符的修饰符，生成原始值的不同版本。

- **EmptyModifier**：一个空修饰符（或标识修饰符），用于在开发过程中在编译时切换修饰符。

- **ModifiedContent**：已应用修饰符的值。

- **ManipulableModifier**
- **ManipulableResponderModifier**
- **ManipulableTransformBindingModifier**
- **ManipulationGeometryModifier**
- **ManipulationGestureModifier**
- **ManipulationUsingGestureStateModifier**
- **Manipulable**：各种可操作相关类型的命名空间。

## 继承自

- 视图修改器


---
source: https://developer.apple.com/documentation/swiftui/environmentalmodifier
crawled: 2025-12-02T17:47:20Z
---

# EnvironmentalModifier

**Protocol**

A modifier that must resolve to a concrete modifier in an environment before use.

## Declaration

```swift
protocol EnvironmentalModifier : ViewModifier where Self.Body == Never
```

## Resolving a modifier

- **resolve(in:)**: Resolve to a concrete modifier in the given `environment`.
- **ResolvedModifier**: The type of modifier to use after being resolved.

## Modifying a view

- **Configuring views**: Adjust the characteristics of a view by applying view modifiers.
- **Reducing view modifier maintenance**: Bundle view modifiers that you regularly reuse into a custom view modifier.
- **modifier(_:)**: Applies a modifier to a view and returns a new view.
- **ViewModifier**: A modifier that you apply to a view or another view modifier, producing a different version of the original value.
- **EmptyModifier**: An empty, or identity, modifier, used during development to switch modifiers at compile time.
- **ModifiedContent**: A value with a modifier applied to it.
- **ManipulableModifier**
- **ManipulableResponderModifier**
- **ManipulableTransformBindingModifier**
- **ManipulationGeometryModifier**
- **ManipulationGestureModifier**
- **ManipulationUsingGestureStateModifier**
- **Manipulable**: A namespace for various manipulable related types.

## Inherits From

- ViewModifier

