---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/supportsImagePlayground
抓取时间： 2025-12-03T06:08:16Z
---

# supportsImagePlayground

**实例属性**

布尔值，表示当前设备是否支持图像生成。

## 声明

```swift
var supportsImagePlayground: Bool { get }
```

## 讨论

当当前设备支持图像生成时，该属性的值为`true`。如果设备或系统不符合生成图像的硬件要求或必要环境（例如以支持的语言运行），则设备可能不支持此功能。

从环境中读取此属性可确定您的应用程序是否可以使用`imagePlaygroundSheet`。

```swift
struct ImageGenerationPresentingView: View {
    @Environment(\.supportsImagePlayground) private var supportsImagePlayground
    @State private var showsImagePlaygroundSheet = false

    var body: some View {
        Button("Open Generation Sheet") {
            showsImagePlaygroundSheet = true
        }
        .disabled(!supportsImagePlayground)
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/supportsImagePlayground
crawled: 2025-12-03T06:08:16Z
---

# supportsImagePlayground

**Instance Property**

A Boolean value that indicates whether image generation is available on the current device.

## Declaration

```swift
var supportsImagePlayground: Bool { get }
```

## Discussion

The value of this property is `true` when the current device supports image generation. A device might not support this feature if the device or system doesn’t meet the hardware requirements or the necessary environment (for example runs in a supported language) to generate the images.

Read this property from the environment to determine if your app can use the `imagePlaygroundSheet`.

```swift
struct ImageGenerationPresentingView: View {
    @Environment(\.supportsImagePlayground) private var supportsImagePlayground
    @State private var showsImagePlaygroundSheet = false

    var body: some View {
        Button("Open Generation Sheet") {
            showsImagePlaygroundSheet = true
        }
        .disabled(!supportsImagePlayground)
    }
}
```

