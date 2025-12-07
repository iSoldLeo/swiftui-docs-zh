--- 来源：https://developer.apple.com/documentation/SwiftUI/View/previewInterfaceOrientation(_:)

抓取时间：2025-12-02T17:04:47Z

---

# previewInterfaceOrientation(_:)

**实例方法**

覆盖预览的屏幕方向。

## 声明

```swift
nonisolated func previewInterfaceOrientation(_ value: InterfaceOrientation) -> some View

```

## 参数

- **value**：用于预览的屏幕方向。

## 返回值

使用给定屏幕方向的预览。

## 说明

默认情况下，设备预览以正向显示，使用屏幕方向 [portrait](../InterfaceOrientation/portrait.zh-Hans.md)。您可以使用 [InterfaceOrientation](../InterfaceOrientation.zh-Hans.md) 结构中的值来更改预览的方向：

```swift
struct CircleImage_Previews: PreviewProvider {
    static var previews: some View {
        CircleImage()
            .previewInterfaceOrientation(.landscapeRight)
    }
}
```

## 自定义预览

- **previewDevice(_:)**：覆盖预览的设备。

- **PreviewDevice**：运行预览的模拟器设备。

- **previewLayout(_:)**：覆盖预览容器的大小。

- **InterfaceOrientation**：从用户视角看到的界面方向。


---
source: https://developer.apple.com/documentation/SwiftUI/View/previewInterfaceOrientation(_:)
crawled: 2025-12-02T17:04:47Z
---

# previewInterfaceOrientation(_:)

**Instance Method**

Overrides the orientation of the preview.

## Declaration

```swift
nonisolated func previewInterfaceOrientation(_ value: InterfaceOrientation) -> some View

```

## Parameters

- **value**: An orientation to use for preview.

## Return Value

A preview that uses the given orientation.

## Discussion

By default, device previews appear right side up, using orientation [portrait](../InterfaceOrientation/portrait.zh-Hans.md). You can change the orientation of a preview using one of the values in the [InterfaceOrientation](../InterfaceOrientation.zh-Hans.md) structure:

```swift
struct CircleImage_Previews: PreviewProvider {
    static var previews: some View {
        CircleImage()
            .previewInterfaceOrientation(.landscapeRight)
    }
}
```

## Customizing a preview

- **previewDevice(_:)**: Overrides the device for a preview.
- **PreviewDevice**: A simulator device that runs a preview.
- **previewLayout(_:)**: Overrides the size of the container for the preview.
- **InterfaceOrientation**: The orientation of the interface from the user’s perspective.

