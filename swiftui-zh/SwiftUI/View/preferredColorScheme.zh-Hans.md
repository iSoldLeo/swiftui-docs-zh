--- 来源：https://developer.apple.com/documentation/SwiftUI/View/preferredColorScheme(_:)

抓取时间：2025-11-30T21:17:49Z

---

# preferredColorScheme(_:)

**实例方法**

设置此视图的首选配色方案。

## 声明

```swift
nonisolated func preferredColorScheme(_ colorScheme: ColorScheme?) -> some View

```

## 参数

- **colorScheme**：此视图的首选配色方案，或 `nil` 表示无偏好。

## 返回值

一个设置了配色方案的视图。

## 说明

将此修饰符与 [ColorScheme](../ColorScheme.zh-Hans.md) 中的值之一结合使用，可以为最近的外层视图（例如弹出框、工作表或窗口）设置首选配色方案。您设置的值会覆盖用户在该演示文稿中选择的深色模式。在下面的示例中，[Toggle](../Toggle.zh-Hans.md) 控制 `isDarkMode` 状态变量，该状态变量又控制包含切换按钮的工作表的配色方案：

```swift
@State private var isPresented = false
@State private var isDarkMode = true

var body: some View {
    Button("Show Sheet") {
        isPresented = true
    }
    .sheet(isPresented: $isPresented) {
        List {
            Toggle("Dark Mode", isOn: $isDarkMode)
        }
        .preferredColorScheme(isDarkMode ? .dark : nil)
    }
}
```

如果您将此修饰符应用于工作表中的任何视图（在本例中为 [List](../List.zh-Hans.md) 和 [Toggle](../Toggle.zh-Hans.md)），则您设置的值会沿着视图层次结构向上传播到包含该视图的演示文稿，直到层次结构中更高层级的另一个配色方案修饰符覆盖它为止。您设置的值也会向下传递到包含该演示文稿的所有子视图。

传递 `nil` 以指示此视图没有首选配色方案。这在仅应有条件地应用首选配色方案的情况下非常有用。在前面的示例中，当 `isDarkMode` 设置为 `true` 时，工作表将优先使用深色模式；否则，将遵循系统确定的配色方案。

同一视图层级结构中的多个视图可以设置首选配色方案。应用此修饰符会覆盖视图中已设置的任何首选配色方案，例如其子视图设置的配色方案。如果视图层级结构中的并行分支设置了相互冲突的非 `nil` 配色方案，系统将根据视图的顺序优先选择第一个非 `nil` 配色方案。在以下示例中，整个视图的首选配色方案将解析为 `.dark`，取自第二个视图：

```swift
VStack {
    Text("First")
        .preferredColorScheme(.light)
        .preferredColorScheme(nil) // overrides `.light`

    Text("Second")
        .preferredColorScheme(.dark)

    Text("Third")
        .preferredColorScheme(.light)
}
```

此修饰符的常见用途是创建同一视图的浅色和深色并排预览：

```swift
struct MyView_Previews: PreviewProvider {
    static var previews: some View {
        MyView().preferredColorScheme(.light)
        MyView().preferredColorScheme(.dark)
    }
}
```

如果您需要检测当前应用于视图的配色方案，请读取 [colorScheme](../EnvironmentValues/colorScheme.zh-Hans.md) 环境值：

```swift
@Environment(\.colorScheme) private var colorScheme

var body: some View {
    Text(colorScheme == .dark ? "Dark" : "Light")
}
```

## 检测并请求浅色或深色外观

- **colorScheme**：此环境的配色方案。

- **ColorScheme**：与浅色和深色外观对应的可用配色方案。


---
source: https://developer.apple.com/documentation/SwiftUI/View/preferredColorScheme(_:)
crawled: 2025-11-30T21:17:49Z
---

# preferredColorScheme(_:)

**Instance Method**

Sets the preferred color scheme for this presentation.

## Declaration

```swift
nonisolated func preferredColorScheme(_ colorScheme: ColorScheme?) -> some View

```

## Parameters

- **colorScheme**: The preferred color scheme for this view, or `nil` to indicate no preference.

## Return Value

A view that sets the color scheme.

## Discussion

Use one of the values in [ColorScheme](../ColorScheme.zh-Hans.md) with this modifier to set a preferred color scheme for the nearest enclosing presentation, like a popover, a sheet, or a window. The value that you set overrides the user’s Dark Mode selection for that presentation. In the example below, the [Toggle](../Toggle.zh-Hans.md) controls an `isDarkMode` state variable, which in turn controls the color scheme of the sheet that contains the toggle:

```swift
@State private var isPresented = false
@State private var isDarkMode = true

var body: some View {
    Button("Show Sheet") {
        isPresented = true
    }
    .sheet(isPresented: $isPresented) {
        List {
            Toggle("Dark Mode", isOn: $isDarkMode)
        }
        .preferredColorScheme(isDarkMode ? .dark : nil)
    }
}
```

If you apply the modifier to any of the views in the sheet — which in this case are a [List](../List.zh-Hans.md) and a [Toggle](../Toggle.zh-Hans.md) — the value that you set propagates up through the view hierarchy to the enclosing presentation, or until another color scheme modifier higher in the hierarchy overrides it. The value you set also flows down to all child views of the enclosing presentation.

Pass `nil` to indicate that there is no preferred color scheme for this view. This is useful in cases where a preferred color scheme should only be applied conditionally. In the previous example, the sheet will prefer dark mode when `isDarkMode` is set to `true`, but otherwise defer to the color scheme as determined by the system.

Multiple views in the same view hierarchy can set a preferred color scheme. Applying this modifier overrides any existing preferred color scheme set for the view, such as by one of its subviews. If there are conflicting, non-`nil` color scheme preferences set by parallel branches of the view hierarchy, the system will prioritize the first non-`nil` preference based on the order of the views. In the example below, the preferred color scheme for the entire view will resolve to `.dark`, from the second view:

```swift
VStack {
    Text("First")
        .preferredColorScheme(.light)
        .preferredColorScheme(nil) // overrides `.light`

    Text("Second")
        .preferredColorScheme(.dark)

    Text("Third")
        .preferredColorScheme(.light)
}
```

A common use for this modifier is to create side-by-side previews of the same view with light and dark appearances:

```swift
struct MyView_Previews: PreviewProvider {
    static var previews: some View {
        MyView().preferredColorScheme(.light)
        MyView().preferredColorScheme(.dark)
    }
}
```

If you need to detect the color scheme that currently applies to a view, read the [colorScheme](../EnvironmentValues/colorScheme.zh-Hans.md) environment value:

```swift
@Environment(\.colorScheme) private var colorScheme

var body: some View {
    Text(colorScheme == .dark ? "Dark" : "Light")
}
```

## Detecting and requesting the light or dark appearance

- **colorScheme**: The color scheme of this environment.
- **ColorScheme**: The possible color schemes, corresponding to the light and dark appearances.

