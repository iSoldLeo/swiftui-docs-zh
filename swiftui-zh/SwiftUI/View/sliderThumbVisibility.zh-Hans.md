--- 来源：https://developer.apple.com/documentation/SwiftUI/View/sliderThumbVisibility(_:)

抓取时间：2025-12-02T17:25:22Z

---

# sliderThumbVisibility(_:)

**实例方法**

设置此视图中滑块的可见性。

## 声明

```swift
nonisolated func sliderThumbVisibility(_ visibility: Visibility) -> some View

```

## 参数

- **visibility**：要应用的滑块可见性。

## 说明

使用此修饰符可以覆盖默认的滑块可见性。例如，以下代码创建了一个没有指示器的滑块：

```swift
@State private var speed = 50.0
@State private var isEditing = false

var body: some View {
    VStack {
        Slider(
            value: $speed,
            in: 0...100,
            onEditingChanged: { editing in
                isEditing = editing
            }
        )
        .sliderThumbVisibility(.hidden)

        Text("\(speed)")
            .foregroundColor(isEditing ? .red : .blue)
    }
}
```

注意：在 watchOS 上，滑块始终可见。


---
source: https://developer.apple.com/documentation/SwiftUI/View/sliderThumbVisibility(_:)
crawled: 2025-12-02T17:25:22Z
---

# sliderThumbVisibility(_:)

**Instance Method**

Sets the thumb visibility for `Slider`s within this view.

## Declaration

```swift
nonisolated func sliderThumbVisibility(_ visibility: Visibility) -> some View

```

## Parameters

- **visibility**: The slider thumb visibility to apply.

## Discussion

Use this modifier to override the default slider thumb visibility. For example, the code below creates a `Slider` without an indicator:

```swift
@State private var speed = 50.0
@State private var isEditing = false

var body: some View {
    VStack {
        Slider(
            value: $speed,
            in: 0...100,
            onEditingChanged: { editing in
                isEditing = editing
            }
        )
        .sliderThumbVisibility(.hidden)

        Text("\(speed)")
            .foregroundColor(isEditing ? .red : .blue)
    }
}
```

Note: On watchOS, the slider thumb is always visible.

