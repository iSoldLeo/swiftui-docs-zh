--- 来源：https://developer.apple.com/documentation/SwiftUI/View/tag(_:includeOptional:)

抓取时间：2025-11-30T19:48:41Z

---

# tag(_:includeOptional:)

**实例方法**

设置此视图的唯一标签值。

## 声明

```swift
nonisolated func tag<V>(_ tag: V, includeOptional: Bool = true) -> some View where V : Hashable

```

## 参数

- **tag**：用作视图标签的 [doc://com.apple.documentation/documentation/Swift/Hashable] 值。

- **includeOptional**：是否也应设置 `Optional<V>` 的标签值。

## 返回值

已设置指定标签的视图。

## 讨论

使用此修饰符可以区分某些可选视图，例如 [Picker](../Picker.zh-Hans.md) 的可能值或 [TabView](../TabView.zh-Hans.md) 的选项卡。标签值可以是符合 [doc://com.apple.documentation/documentation/Swift/Hashable] 协议的任何类型。

此修饰符将写入类型为 `V` 的标签值，如果启用了 `includeOptional`，则还会写入类型为 `Optional<V>` 的标签值。检查任一类型标签的容器都会看到该值已设置。

在下面的示例中，视图构建器 [Picker](../Picker.zh-Hans.md) 中的 [ForEach](../ForEach.zh-Hans.md) 循环遍历 `Flavor` 枚举。它提取每个枚举元素的字符串值，用于构建行标签，并将枚举值作为 `tag(_:)` 修饰符的输入。

```swift
struct FlavorPicker: View {
    enum Flavor: String, CaseIterable, Identifiable {
        case chocolate, vanilla, strawberry
        var id: Self { self }
    }

    @State private var selectedFlavor: Flavor? = nil

    var body: some View {
        Picker("Flavor", selection: $selectedFlavor) {
            ForEach(Flavor.allCases) { flavor in
                Text(flavor.rawValue)
                    .tag(flavor)
            }
        }
    }
}
```

[Picker](../Picker.zh-Hans.md) 的选择类型为 `Optional<Flavor>`，因此它会在其内容中查找 `Optional<Flavor>` 类型的标签。由于标签修饰符默认启用 `includeOptional`，即使每个选项的标签都是非可选的 `Flavor`，标签修饰符也会同时写入非可选和可选版本的值，从而允许 [Picker](../Picker.zh-Hans.md) 选择内容。

[ForEach](../ForEach.zh-Hans.md) 会自动使用对应元素的 `id` 参数为每个枚举视图应用默认标签。如果元素的 `id` 参数和选择器的 `selection` 输入类型完全相同，或者类型相同但为可选，则可以省略显式标签修饰符。

要查看不需要显式标签的示例，请参阅 [Picker](../Picker.zh-Hans.md)。

## 管理视图层次结构

- **id(_:)**：将视图的标识绑定到给定的代理值。

- **equatable()**：防止视图在新值与其旧值相同时更新其子视图。


---
source: https://developer.apple.com/documentation/SwiftUI/View/tag(_:includeOptional:)
crawled: 2025-11-30T19:48:41Z
---

# tag(_:includeOptional:)

**Instance Method**

Sets the unique tag value of this view.

## Declaration

```swift
nonisolated func tag<V>(_ tag: V, includeOptional: Bool = true) -> some View where V : Hashable

```

## Parameters

- **tag**: A [doc://com.apple.documentation/documentation/Swift/Hashable] value to use as the view’s tag.
- **includeOptional**: If the tag value for `Optional<V>` should also be set.

## Return Value

A view with the specified tag set.

## Discussion

Use this modifier to differentiate among certain selectable views, like the possible values of a [Picker](../Picker.zh-Hans.md) or the tabs of a [TabView](../TabView.zh-Hans.md). Tag values can be of any type that conforms to the [doc://com.apple.documentation/documentation/Swift/Hashable] protocol.

This modifier will write the tag value for the type `V`, as well as `Optional<V>` if `includeOptional` is enabled. Containers checking for tags of either type will see the value as set.

In the example below, the [ForEach](../ForEach.zh-Hans.md) loop in the [Picker](../Picker.zh-Hans.md) view builder iterates over the `Flavor` enumeration. It extracts the string value of each enumeration element for use in constructing the row label, and uses the enumeration value as input to the `tag(_:)` modifier.

```swift
struct FlavorPicker: View {
    enum Flavor: String, CaseIterable, Identifiable {
        case chocolate, vanilla, strawberry
        var id: Self { self }
    }

    @State private var selectedFlavor: Flavor? = nil

    var body: some View {
        Picker("Flavor", selection: $selectedFlavor) {
            ForEach(Flavor.allCases) { flavor in
                Text(flavor.rawValue)
                    .tag(flavor)
            }
        }
    }
}
```

The selection type of the [Picker](../Picker.zh-Hans.md) is an `Optional<Flavor>` and so it will look for tags on its contents of `Optional<Flavor>` type. Since the tag modifier defaults to having `includeOptional` enabled, even though the tag for each option is a non-optional `Flavor`, the tag modifier writes values for both the non-optional, and optional versions of the value, allowing the contents to be selectable by the [Picker](../Picker.zh-Hans.md).

A [ForEach](../ForEach.zh-Hans.md) automatically applies a default tag to each enumerated view using the `id` parameter of the corresponding element. If the element’s `id` parameter and the picker’s `selection` input have exactly the same type, or the same type but optional, you can omit the explicit tag modifier.

To see examples that don’t require an explicit tag, see [Picker](../Picker.zh-Hans.md).

## Managing the view hierarchy

- **id(_:)**: Binds a view’s identity to the given proxy value.
- **equatable()**: Prevents the view from updating its child view when its new value is the same as its old value.

