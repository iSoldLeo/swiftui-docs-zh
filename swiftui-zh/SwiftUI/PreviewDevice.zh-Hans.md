--- 来源：https://developer.apple.com/documentation/SwiftUI/PreviewDevice
抓取时间：2025-12-02T17:46:02Z

---

# PreviewDevice

**Structure**

运行预览的模拟器设备。

## 声明

```swift
struct PreviewDevice
```

## 概述

按名称（例如“iPhone X”）或型号（例如“iPad8,1”）创建预览设备。在调用 [previewDevice(_:)](View/previewDevice.zh-Hans.md) 修饰符时使用该设备，可以设置一个预览设备，该设备在 Xcode 中更改运行目标时不会改变：

```swift
struct CircleImage_Previews: PreviewProvider {
    static var previews: some View {
        CircleImage()
            .previewDevice(PreviewDevice(rawValue: "iPad Pro (11-inch)"))
    }
}
```

您可以使用终端应用程序中的 `xcrun` 命令获取支持的预览设备名称列表：

```swift
% xcrun simctl list devicetypes
```

此外，您还可以使用以下值进行 macOS 平台开发：

- “Mac”

- “Mac Catalyst”

## 自定义预览

- **previewDevice(_:)**：覆盖预览的设备。

- **previewLayout(_:)**：覆盖预览容器的大小。

- **previewInterfaceOrientation(_:)**：覆盖预览的方向。

- **InterfaceOrientation**：从用户角度看界面的方向。

## 符合以下标准

- ExpressibleByExtendedGraphemeClusterLiteral

- ExpressibleByStringLiteral

- ExpressibleByUnicodeScalarLiteral

- RawRepresentable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/PreviewDevice
crawled: 2025-12-02T17:46:02Z
---

# PreviewDevice

**Structure**

A simulator device that runs a preview.

## Declaration

```swift
struct PreviewDevice
```

## Overview

Create a preview device by name, like “iPhone X”, or by model number, like “iPad8,1”. Use the device in a call to the [previewDevice(_:)](View/previewDevice.zh-Hans.md) modifier to set a preview device that doesn’t change when you change the run destination in Xcode:

```swift
struct CircleImage_Previews: PreviewProvider {
    static var previews: some View {
        CircleImage()
            .previewDevice(PreviewDevice(rawValue: "iPad Pro (11-inch)"))
    }
}
```

You can get a list of supported preview device names by using the `xcrun` command in the Terminal app:

```swift
% xcrun simctl list devicetypes
```

Additionally, you can use the following values for macOS platform development:

- “Mac”
- “Mac Catalyst”

## Customizing a preview

- **previewDevice(_:)**: Overrides the device for a preview.
- **previewLayout(_:)**: Overrides the size of the container for the preview.
- **previewInterfaceOrientation(_:)**: Overrides the orientation of the preview.
- **InterfaceOrientation**: The orientation of the interface from the user’s perspective.

## Conforms To

- ExpressibleByExtendedGraphemeClusterLiteral
- ExpressibleByStringLiteral
- ExpressibleByUnicodeScalarLiteral
- RawRepresentable
- Sendable
- SendableMetatype

