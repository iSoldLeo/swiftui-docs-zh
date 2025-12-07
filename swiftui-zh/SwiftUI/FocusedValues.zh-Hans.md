---
来源： https://developer.apple.com/documentation/SwiftUI/FocusedValues
抓取时间： 2025-12-02T17:43:11Z
---

# FocusedValues

**Structure**

被聚焦的场景或视图及其祖先输出的状态集合。

## 声明

```swift
struct FocusedValues
```

## 创建自定义焦点值

使用`Entry` 宏，通过用新属性扩展 `FocusedValues` 来创建自定义聚焦值：

```swift
extension FocusedValues {
    @Entry var focusedDocument: Binding<MyDocument>?
}
```

`Entry`宏会自动生成底层键类型，并为聚焦值提供 getter 和 setter。由于重点值的默认值总是 `nil`，因此所有重点值都必须是可选的。

### 在视图中发布值

视图使用[focusedValue(_:_:)](View/focusedValue.zh-Hans.md)修饰符来发布焦点值：

```swift
struct DocumentCellView: View {
    @Binding var document: MyDocument

    var body: some View {
        Text("Document Content")
            .focusedValue(\.focusedDocument, $document)
    }
}
```

对于场景范围内的值，应根据所关注的场景使用[focusedSceneValue(_:_:)](View/focusedSceneValue.zh-Hans.md)：

```swift
struct DocumentViewer: View {
    @Binding var document: MyDocument

    var body: some View {
        Text("Document Content")
            .focusedSceneValue(\.focusedDocument, $document)
    }
}
```

### 访问当前聚焦值

在您的[App](App.zh-Hans.md) 或[View](View.zh-Hans.md) 中使用[FocusedValue](FocusedValue.zh-Hans.md) 属性包装器读取`body` 中的当前值。如果重点值的值类型是`Binding`，则[FocusedBinding](FocusedBinding.zh-Hans.md)可用作访问`wrappedValue`的便捷方法：

```swift
@main
struct DocumentApp: App {
    @FocusedBinding(\.focusedDocument) var currentDocument: MyDocument?

    var body: some Scene {
        DocumentGroup(newDocument: MyDocument()) { file in
            ContentView(document: file.$document)
                .focusedValue(\.focusedDocument, file.$document)
        }
        .commands {
            CommandGroup(after: .undoRedo) {
                Button("Increment") {
                    currentDocument?.value += 1
                }.disabled(currentDocument == nil)
            }
        }
    }
}
```

## 获取键值

- **subscript(_:)**：读取和写入与给定重点值键相关的值。

## 向焦点视图公开值类型

- **focusedValue(_:)**：设置给定对象类型的焦点值。
- **focusedValue(_:_:)**：通过注入一个值来修改该视图，该值由您提供给状态依赖于聚焦视图层次结构的其他视图使用。
- **focusedSceneValue(_:)**：在全场景范围内设置给定对象类型的焦点值。
- **focusedSceneValue(_:_:)**：通过注入一个值来修改此视图，该值由您提供给状态依赖于聚焦场景的其他视图使用。

## 符合

- 可复制
- 等价


---
source: https://developer.apple.com/documentation/SwiftUI/FocusedValues
crawled: 2025-12-02T17:43:11Z
---

# FocusedValues

**Structure**

A collection of state exported by the focused scene or view and its ancestors.

## Declaration

```swift
struct FocusedValues
```

## Creating Custom Focused Values

Use the `Entry` macro to create custom focused values by extending `FocusedValues` with new properties:

```swift
extension FocusedValues {
    @Entry var focusedDocument: Binding<MyDocument>?
}
```

The `Entry` macro automatically generates the underlying key type and provides the getter and setter for the focused value. Since the default value for focused values is always `nil`, all focused values must be optional.

### Publishing Values in Your Views

Views publish focused values using the [focusedValue(_:_:)](View/focusedValue.zh-Hans.md) modifier:

```swift
struct DocumentCellView: View {
    @Binding var document: MyDocument

    var body: some View {
        Text("Document Content")
            .focusedValue(\.focusedDocument, $document)
    }
}
```

For scene-wide values that should be available depending on the focused scene, use [focusedSceneValue(_:_:)](View/focusedSceneValue.zh-Hans.md):

```swift
struct DocumentViewer: View {
    @Binding var document: MyDocument

    var body: some View {
        Text("Document Content")
            .focusedSceneValue(\.focusedDocument, $document)
    }
}
```

### Accessing the current focused value

Use the [FocusedValue](FocusedValue.zh-Hans.md) property wrapper in your [App](App.zh-Hans.md) or [View](View.zh-Hans.md) to read the current value in the `body`. The [FocusedBinding](FocusedBinding.zh-Hans.md) can be used as a convenient way to access the `wrappedValue` if the value type of the focused value is a `Binding`:

```swift
@main
struct DocumentApp: App {
    @FocusedBinding(\.focusedDocument) var currentDocument: MyDocument?

    var body: some Scene {
        DocumentGroup(newDocument: MyDocument()) { file in
            ContentView(document: file.$document)
                .focusedValue(\.focusedDocument, file.$document)
        }
        .commands {
            CommandGroup(after: .undoRedo) {
                Button("Increment") {
                    currentDocument?.value += 1
                }.disabled(currentDocument == nil)
            }
        }
    }
}
```

## Getting the value for a key

- **subscript(_:)**: Reads and writes values associated with a given focused value key.

## Exposing value types to focused views

- **focusedValue(_:)**: Sets the focused value for the given object type.
- **focusedValue(_:_:)**: Modifies this view by injecting a value that you provide for use by other views whose state depends on the focused view hierarchy.
- **focusedSceneValue(_:)**: Sets the focused value for the given object type at a scene-wide scope.
- **focusedSceneValue(_:_:)**: Modifies this view by injecting a value that you provide for use by other views whose state depends on the focused scene.

## Conforms To

- Copyable
- Equatable

