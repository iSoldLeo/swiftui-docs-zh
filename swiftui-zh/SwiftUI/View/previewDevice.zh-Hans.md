--- 来源：https://developer.apple.com/documentation/SwiftUI/View/previewDevice(_:)

抓取时间：2025-12-02T17:46:01Z

---

# previewDevice(_:)

**实例方法**

覆盖预览设备。

## 声明

```swift
nonisolated func previewDevice(_ value: PreviewDevice?) -> some View

```

## 参数

- **value**：用于预览的设备，或 `nil`：让 Xcode 根据运行目标自动选择设备。

## 返回值

使用指定设备的预览。

## 说明

默认情况下，Xcode 会根据当前选择的运行目标自动选择预览设备。如果您想选择一个不会因 Xcode 设置而改变的设备，请提供一个 [PreviewDevice](../PreviewDevice.zh-Hans.md) 实例，并使用特定设备的名称或型号对其进行初始化：

```swift
struct CircleImage_Previews: PreviewProvider {
    static var previews: some View {
        CircleImage()
            .previewDevice(PreviewDevice(rawValue: "iPad Pro (11-inch)"))
    }
}
```

您可以使用终端应用中的 `xcrun` 命令获取支持的预览设备名称列表，例如“iPhone 11”、“iPad Pro (11 英寸)”和“Apple Watch Series 5 - 44 毫米”：

```swift
% xcrun simctl list devicetypes
```

此外，您还可以使用以下值进行 macOS 平台开发：

- “Mac”

- “Mac Catalyst”

## 自定义预览

- **PreviewDevice**：运行预览的模拟器设备。

- **previewLayout(_:)**：覆盖预览容器的大小。

- **previewInterfaceOrientation(_:)**：覆盖预览的方向。

- **InterfaceOrientation**：从用户视角看界面的方向。


---
source: https://developer.apple.com/documentation/SwiftUI/View/previewDevice(_:)
crawled: 2025-12-02T17:46:01Z
---

# previewDevice(_:)

**Instance Method**

Overrides the device for a preview.

## Declaration

```swift
nonisolated func previewDevice(_ value: PreviewDevice?) -> some View

```

## Parameters

- **value**: A device to use for preview, or `nil` to let Xcode automatically choose a device based on the run destination.

## Return Value

A preview that uses the given device.

## Discussion

By default, Xcode automatically chooses a preview device based on your currently selected run destination. If you want to choose a device that doesn’t change based on Xcode settings, provide a [PreviewDevice](../PreviewDevice.zh-Hans.md) instance that you initialize with the name or model of a specific device:

```swift
struct CircleImage_Previews: PreviewProvider {
    static var previews: some View {
        CircleImage()
            .previewDevice(PreviewDevice(rawValue: "iPad Pro (11-inch)"))
    }
}
```

You can get a list of supported preview device names, like “iPhone 11”, “iPad Pro (11-inch)”, and “Apple Watch Series 5 - 44mm”, by using the `xcrun` command in the Terminal app:

```swift
% xcrun simctl list devicetypes
```

Additionally, you can use the following values for macOS platform development:

- “Mac”
- “Mac Catalyst”

## Customizing a preview

- **PreviewDevice**: A simulator device that runs a preview.
- **previewLayout(_:)**: Overrides the size of the container for the preview.
- **previewInterfaceOrientation(_:)**: Overrides the orientation of the preview.
- **InterfaceOrientation**: The orientation of the interface from the user’s perspective.

