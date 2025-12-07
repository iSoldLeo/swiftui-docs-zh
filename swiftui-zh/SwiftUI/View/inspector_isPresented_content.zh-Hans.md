--- 来源：https://developer.apple.com/documentation/SwiftUI/View/inspector(isPresented:content:)

抓取时间：2025-11-30T21:16:02Z

---

# inspector(isPresented:content:)

**实例方法**

在视图层级结构中指定的位置插入一个检查器。

## 声明

```swift
nonisolated func inspector<V>(isPresented: Binding<Bool>, @ViewBuilder content: () -> V) -> some View where V : View

```

## 参数

- **isPresented**：绑定到 `Bool` 的属性，用于控制显示状态。

- **content**：检查器内容。

## 说明

应用此修饰符可声明一个具有上下文相关显示方式的检查器。例如，检查器可以以常规尺寸类别中的列的形式显示，但在水平紧凑尺寸类别中，它可以适应整个工作表。

```swift
struct ShapeEditor: View {
    @State var presented: Bool = false
    var body: some View {
        MyEditorView()
            .inspector(isPresented: $presented) {
                TextTraitsInspectorView()
            }
    }
}
```

## 显示检查器

- **inspectorColumnWidth(_:)**：设置以列的形式显示此视图的检查器的固定首选宽度。

- **inspectorColumnWidth(min:ideal:max:)**：设置以列的形式显示检查器的灵活首选宽度。


---
source: https://developer.apple.com/documentation/SwiftUI/View/inspector(isPresented:content:)
crawled: 2025-11-30T21:16:02Z
---

# inspector(isPresented:content:)

**Instance Method**

Inserts an inspector at the applied position in the view hierarchy.

## Declaration

```swift
nonisolated func inspector<V>(isPresented: Binding<Bool>, @ViewBuilder content: () -> V) -> some View where V : View

```

## Parameters

- **isPresented**: A binding to `Bool` controlling the presented state.
- **content**: The inspector content.

## Discussion

Apply this modifier to declare an inspector with a context-dependent presentation. For example, an inspector can present as a trailing column in a horizontally regular size class, but adapt to a sheet in a horizontally compact size class.

```swift
struct ShapeEditor: View {
    @State var presented: Bool = false
    var body: some View {
        MyEditorView()
            .inspector(isPresented: $presented) {
                TextTraitsInspectorView()
            }
    }
}
```





## Presenting an inspector

- **inspectorColumnWidth(_:)**: Sets a fixed, preferred width for the inspector containing this view when presented as a trailing column.
- **inspectorColumnWidth(min:ideal:max:)**: Sets a flexible, preferred width for the inspector in a trailing-column presentation.

