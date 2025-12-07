---
来源： https://developer.apple.com/documentation/swiftui/emptymodifier
抓取时间： 2025-12-02T17:47:19Z
---

# 空修改器

**Structure**

空修饰符或标识符，在开发过程中用于在编译时切换修饰符。

### 声明

```swift
@frozen struct EmptyModifier
```

## 概览

在开发过程中，使用空修饰符可在编译时切换修饰符。在下面的示例中，在调试构建中，`ContentView` 中的[Text](Text.zh-Hans.md) 视图的背景为黄色，边框为红色。非调试构建反映的是默认系统或容器提供的外观。

```swift
struct EmphasizedLayout: ViewModifier {
    func body(content: Content) -> some View {
        content
            .background(Color.yellow)
            .border(Color.red)
    }
}

struct ContentView: View {
    var body: some View {
        Text("Hello, World!")
            .modifier(modifier)
    }

    var modifier: some ViewModifier {
        #if DEBUG
            return EmphasizedLayout()
        #else
            return EmptyModifier()
        #endif
    }
}
```

## 创建空修饰符

- **init()**

## 获取身份修饰符

- **identity**

## 修改视图

- 配置视图**：通过应用视图修改器调整视图的特性。
- 减少视图修改器的维护**：将经常重复使用的视图修改器打包到自定义视图修改器中。
- **modifier(_:)**：将修改器应用到视图并返回新视图。
- **ViewModifier**：将修改器应用到视图或其他视图修改器，生成原始值的不同版本。
- **ModifiedContent**：应用了修改器的值。
- **EnvironmentalModifier**：在使用前必须在环境中解析为具体修饰符的修饰符。
- **ManipulableModifier**：修饰符。
- **ManipulableResponderModifier**：修饰语。
- **ManipulableTransformBindingModifier**
- **ManipulationGeometryModifier**
- **ManipulationGestureModifier**
- **ManipulationUsingGestureStateModifier**
- **Manipulable**：各种可操作相关类型的命名空间。

## 符合

- 比特可复制
- 可复制
- 可发送
- 可发送元类型
- 视图修改器


---
source: https://developer.apple.com/documentation/swiftui/emptymodifier
crawled: 2025-12-02T17:47:19Z
---

# EmptyModifier

**Structure**

An empty, or identity, modifier, used during development to switch modifiers at compile time.

## Declaration

```swift
@frozen struct EmptyModifier
```

## Overview

Use the empty modifier to switch modifiers at compile time during development. In the example below, in a debug build the [Text](Text.zh-Hans.md) view inside `ContentView` has a yellow background and a red border. A non-debug build reflects the default system, or container supplied appearance.

```swift
struct EmphasizedLayout: ViewModifier {
    func body(content: Content) -> some View {
        content
            .background(Color.yellow)
            .border(Color.red)
    }
}

struct ContentView: View {
    var body: some View {
        Text("Hello, World!")
            .modifier(modifier)
    }

    var modifier: some ViewModifier {
        #if DEBUG
            return EmphasizedLayout()
        #else
            return EmptyModifier()
        #endif
    }
}
```

## Creating an empty modifier

- **init()**

## Getting the identity modifier

- **identity**

## Modifying a view

- **Configuring views**: Adjust the characteristics of a view by applying view modifiers.
- **Reducing view modifier maintenance**: Bundle view modifiers that you regularly reuse into a custom view modifier.
- **modifier(_:)**: Applies a modifier to a view and returns a new view.
- **ViewModifier**: A modifier that you apply to a view or another view modifier, producing a different version of the original value.
- **ModifiedContent**: A value with a modifier applied to it.
- **EnvironmentalModifier**: A modifier that must resolve to a concrete modifier in an environment before use.
- **ManipulableModifier**
- **ManipulableResponderModifier**
- **ManipulableTransformBindingModifier**
- **ManipulationGeometryModifier**
- **ManipulationGestureModifier**
- **ManipulationUsingGestureStateModifier**
- **Manipulable**: A namespace for various manipulable related types.

## Conforms To

- BitwiseCopyable
- Copyable
- Sendable
- SendableMetatype
- ViewModifier

