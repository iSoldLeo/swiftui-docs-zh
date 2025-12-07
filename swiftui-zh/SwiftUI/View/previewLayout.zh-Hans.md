--- 来源：https://developer.apple.com/documentation/SwiftUI/View/previewLayout(_:)

抓取时间：2025-12-02T17:46:02Z

---

# previewLayout(_:)

**实例方法**

覆盖预览容器的大小。

## 声明

```swift
nonisolated func previewLayout(_ value: PreviewLayout) -> some View

```

## 参数

- **value**：用于预览的布局。

## 返回值

使用给定布局的预览。

## 说明

默认情况下，预览使用 `PreviewLayout/device` 布局，该布局将视图放置在所选设备的视觉表示中。您也可以通过选择 `PreviewLayout` 值之一来指定预览使用不同的布局，例如 `PreviewLayout/sizeThatFits`：

```swift
struct CircleImage_Previews: PreviewProvider {
    static var previews: some View {
        CircleImage()
            .previewLayout(.sizeThatFits)
    }
}
```

## 自定义预览

- **previewDevice(_:)**：覆盖预览的设备。

- **PreviewDevice**：运行预览的模拟器设备。

- **previewInterfaceOrientation(_:)**：覆盖预览的方向。

- **InterfaceOrientation**：从用户视角看到的界面方向。


---
source: https://developer.apple.com/documentation/SwiftUI/View/previewLayout(_:)
crawled: 2025-12-02T17:46:02Z
---

# previewLayout(_:)

**Instance Method**

Overrides the size of the container for the preview.

## Declaration

```swift
nonisolated func previewLayout(_ value: PreviewLayout) -> some View

```

## Parameters

- **value**: A layout to use for preview.

## Return Value

A preview that uses the given layout.

## Discussion

By default, previews use the `PreviewLayout/device` layout, which places the view inside a visual representation of the chosen device. You can instead tell a preview to use a different layout by choosing one of the `PreviewLayout` values, like `PreviewLayout/sizeThatFits`:

```swift
struct CircleImage_Previews: PreviewProvider {
    static var previews: some View {
        CircleImage()
            .previewLayout(.sizeThatFits)
    }
}
```

## Customizing a preview

- **previewDevice(_:)**: Overrides the device for a preview.
- **PreviewDevice**: A simulator device that runs a preview.
- **previewInterfaceOrientation(_:)**: Overrides the orientation of the preview.
- **InterfaceOrientation**: The orientation of the interface from the user’s perspective.

