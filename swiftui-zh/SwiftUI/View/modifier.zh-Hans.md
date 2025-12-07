--- 来源：https://developer.apple.com/documentation/swiftui/view/modifier(_:)

抓取时间：2025-11-30T21:32:10Z

---

# modifier(_:)

**实例方法**

将修饰符应用于视图并返回一个新视图。

## 声明

```swift
nonisolated func modifier<T>(_ modifier: T) -> ModifiedContent<Self, T>
```

## 参数

- **modifier**：要应用于此视图的修饰符。

## 说明

使用此修饰符可以组合 [View](../View.zh-Hans.md) 和 [ViewModifier](../ViewModifier.zh-Hans.md)，以创建一个新视图。例如，如果您为一种新型标题（蓝色文本，外加圆角矩形框）创建视图修饰符：

```swift
struct BorderedCaption: ViewModifier {
    func body(content: Content) -> some View {
        content
            .font(.caption2)
            .padding(10)
            .overlay(
                RoundedRectangle(cornerRadius: 15)
                    .stroke(lineWidth: 1)
            )
            .foregroundColor(Color.blue)
    }
}
```

您可以使用 [modifier(_:)](modifier.zh-Hans.md) 扩展 [View](../View.zh-Hans.md)，从而创建一个新的修饰符，用于应用上面定义的 `BorderedCaption`：

```swift
extension View {
    func borderedCaption() -> some View {
        modifier(BorderedCaption())
    }
}
```

然后，您可以将带边框的标题应用于任何视图：

```swift
Image(systemName: "bus")
    .resizable()
    .frame(width:50, height:50)
Text("Downtown Bus")
    .borderedCaption()
```

## 修改视图

- **配置视图**：通过应用视图修饰符来调整视图的特性。

- **减少视图修饰符的维护**：将您经常重复使用的视图修饰符捆绑到一个自定义视图修饰符中。

- **ViewModifier**：您可以将其应用于视图或其他视图修饰符，从而生成原始值的不同版本。

- **EmptyModifier**：一个空修饰符（或标识修饰符），用于在开发过程中在编译时切换修饰符。

- **ModifiedContent**：一个应用了修饰符的值。

- **EnvironmentalModifier**：一个修饰符，在使用前必须在环境中解析为具体的修饰符。

- **ManipulableModifier**

- **ManipulableResponderModifier**

- **ManipulableTransformBindingModifier**

- **ManipulationGeometryModifier**

- **ManipulationGestureModifier**

- **ManipulationUsingGestureStateModifier**

- **Manipulable**：一个用于各种可操作相关类型的命名空间。


---
source: https://developer.apple.com/documentation/swiftui/view/modifier(_:)
crawled: 2025-11-30T21:32:10Z
---

# modifier(_:)

**Instance Method**

Applies a modifier to a view and returns a new view.

## Declaration

```swift
nonisolated func modifier<T>(_ modifier: T) -> ModifiedContent<Self, T>
```

## Parameters

- **modifier**: The modifier to apply to this view.

## Discussion

Use this modifier to combine a [View](../View.zh-Hans.md) and a [ViewModifier](../ViewModifier.zh-Hans.md), to create a new view. For example, if you create a view modifier for a new kind of caption with blue text surrounded by a rounded rectangle:

```swift
struct BorderedCaption: ViewModifier {
    func body(content: Content) -> some View {
        content
            .font(.caption2)
            .padding(10)
            .overlay(
                RoundedRectangle(cornerRadius: 15)
                    .stroke(lineWidth: 1)
            )
            .foregroundColor(Color.blue)
    }
}
```

You can use [modifier(_:)](modifier.zh-Hans.md) to extend [View](../View.zh-Hans.md) to create new modifier for applying the `BorderedCaption` defined above:

```swift
extension View {
    func borderedCaption() -> some View {
        modifier(BorderedCaption())
    }
}
```

Then you can apply the bordered caption to any view:

```swift
Image(systemName: "bus")
    .resizable()
    .frame(width:50, height:50)
Text("Downtown Bus")
    .borderedCaption()
```



## Modifying a view

- **Configuring views**: Adjust the characteristics of a view by applying view modifiers.
- **Reducing view modifier maintenance**: Bundle view modifiers that you regularly reuse into a custom view modifier.
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
- **Manipulable**: A namespace for various manipulable related types.

