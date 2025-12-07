--- 来源：https://developer.apple.com/documentation/swiftui/manipulable
抓取时间：2025-12-02T17:47:50Z

---

# Manipulable

**Enumeration**

用于各种 Manipulable 相关类型的命名空间。

## 声明

```swift
enum Manipulable
```

## 结构体

- **Manipulable.Event**：描述操作手势期间生成的事件。

- **Manipulable.GestureState**：描述操作手势的状态。

- **Manipulable.Inertia**：描述视图的惯性，定义视图抵抗操作的程度。

- **Manipulable.InputDevice**：描述输入设备，例如手或触控板。

- **Manipulable.Operation**：描述用户操作视图时对视图执行的操作。

## 修改视图

- **配置视图**：通过应用视图修饰符来调整视图的特性。

- **减少视图修饰符的维护**：将经常重复使用的视图修饰符打包成一个自定义视图修饰符。

- **modifier(_:)**：将修饰符应用于视图并返回一个新视图。

- **ViewModifier**：应用于视图或其他视图修饰符的修饰符，生成原始值的不同版本。

- **EmptyModifier**：一个空修饰符（或标识修饰符），用于在开发过程中在编译时切换修饰符。

- **ModifiedContent**：应用了修饰符的值。

- **EnvironmentalModifier**：使用前必须解析为环境中的具体修改器的修改器。
- **ManipulableModifier**
- **ManipulableResponderModifier**
- **ManipulableTransformBindingModifier**
- **ManipulationGeometryModifier**
- **ManipulationGestureModifier**
- **ManipulationUsingGestureStateModifier**

## 符合

- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/swiftui/manipulable
crawled: 2025-12-02T17:47:50Z
---

# Manipulable

**Enumeration**

A namespace for various manipulable related types.

## Declaration

```swift
enum Manipulable
```

## Structures

- **Manipulable.Event**: Describes an event generated during a manipulation gesture.
- **Manipulable.GestureState**: Describes the state of a manipulation gesture.
- **Manipulable.Inertia**: Describes inertia of a view that defines how much a view resists being manipulated.
- **Manipulable.InputDevice**: Describes an input device like a hand or a trackpad.
- **Manipulable.Operation**: Describes an operation applied to a view when a person is manipulating a view.

## Modifying a view

- **Configuring views**: Adjust the characteristics of a view by applying view modifiers.
- **Reducing view modifier maintenance**: Bundle view modifiers that you regularly reuse into a custom view modifier.
- **modifier(_:)**: Applies a modifier to a view and returns a new view.
- **ViewModifier**: A modifier that you apply to a view or another view modifier, producing a different version of the original value.
- **EmptyModifier**: An empty, or identity, modifier, used during development to switch modifiers at compile time.
- **ModifiedContent**: A value with a modifier applied to it.
- **EnvironmentalModifier**: A modifier that must resolve to a concrete modifier in an environment before use.
- **ManipulableModifier**
- **ManipulableResponderModifier**
- **ManipulableTransformBindingModifier**
- **ManipulationGeometryModifier**
- **ManipulationGestureModifier**
- **ManipulationUsingGestureStateModifier**

## Conforms To

- Sendable
- SendableMetatype

