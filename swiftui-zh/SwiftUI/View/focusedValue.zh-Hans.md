--- 来源：https://developer.apple.com/documentation/SwiftUI/View/focusedValue(_:_:)

抓取时间：2025-12-02T17:43:09Z

---

# focusedValue(_:_:)

**实例方法**

通过注入您提供的值来修改此视图，该值可供其他状态依赖于当前焦点视图层次结构的视图使用。

## 声明

```swift
nonisolated func focusedValue<Value>(_ keyPath: WritableKeyPath<FocusedValues, Value?>, _ value: Value) -> some View

```

## 参数

- **keyPath**：将 `value` 添加到现有导出焦点值表时要关联的键路径。

- **value**：要导出的焦点值。

## 返回值

此视图的修改表示。

## 向聚焦视图公开值类型

- **focusedValue(_:)**：设置给定对象类型的聚焦值。

- **focusedSceneValue(_:)**：在场景范围内设置给定对象类型的聚焦值。

- **focusedSceneValue(_:_:)**：通过注入您提供的值来修改此视图，供状态依赖于聚焦场景的其他视图使用。

- **FocusedValues**：聚焦场景或视图及其祖先导出的状态集合。


---
source: https://developer.apple.com/documentation/SwiftUI/View/focusedValue(_:_:)
crawled: 2025-12-02T17:43:09Z
---

# focusedValue(_:_:)

**Instance Method**

Modifies this view by injecting a value that you provide for use by other views whose state depends on the focused view hierarchy.

## Declaration

```swift
nonisolated func focusedValue<Value>(_ keyPath: WritableKeyPath<FocusedValues, Value?>, _ value: Value) -> some View

```

## Parameters

- **keyPath**: The key path to associate `value` with when adding it to the existing table of exported focus values.
- **value**: The focus value to export.

## Return Value

A modified representation of this view.

## Exposing value types to focused views

- **focusedValue(_:)**: Sets the focused value for the given object type.
- **focusedSceneValue(_:)**: Sets the focused value for the given object type at a scene-wide scope.
- **focusedSceneValue(_:_:)**: Modifies this view by injecting a value that you provide for use by other views whose state depends on the focused scene.
- **FocusedValues**: A collection of state exported by the focused scene or view and its ancestors.

