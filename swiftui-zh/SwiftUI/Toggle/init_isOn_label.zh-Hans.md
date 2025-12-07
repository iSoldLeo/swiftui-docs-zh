---
来源：https://developer.apple.com/documentation/SwiftUI/Toggle/init(isOn:label:)
抓取时间：2025-12-01T02:45:28Z
---

# init(isOn:label:)

**Initializer**

创建显示自定义标签的切换按钮。

## 声明

```swift
init(isOn: Binding<Bool>, @ViewBuilder label: () -> Label)
```

## 参数

- **isOn**：与属性的绑定，该属性决定切换是开还是关。
- **label**：描述切换目的的视图。

## 创建切换

- **init(_:isOn:)**：创建一个通过本地化字符串键生成标签的切换框。
- **init(_:image:isOn:)**：创建可通过本地化字符串键和图像资源生成标签的切换按钮。
- **init(_:systemImage:isOn:)**：创建根据本地化字符串键和系统图像生成标签的切换按钮。


---
source: https://developer.apple.com/documentation/SwiftUI/Toggle/init(isOn:label:)
crawled: 2025-12-01T02:45:28Z
---

# init(isOn:label:)

**Initializer**

Creates a toggle that displays a custom label.

## Declaration

```swift
init(isOn: Binding<Bool>, @ViewBuilder label: () -> Label)
```

## Parameters

- **isOn**: A binding to a property that determines whether the toggle is on or off.
- **label**: A view that describes the purpose of the toggle.

## Creating a toggle

- **init(_:isOn:)**: Creates a toggle that generates its label from a localized string key.
- **init(_:image:isOn:)**: Creates a toggle that generates its label from a localized string key and image resource.
- **init(_:systemImage:isOn:)**: Creates a toggle that generates its label from a localized string key and system image.

