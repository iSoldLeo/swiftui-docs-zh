--- 来源：https://developer.apple.com/documentation/SwiftUI/Material/materialActiveAppearance(_:)

抓取时间：2025-12-03T04:53:48Z

---

# materialActiveAppearance(_:)

**实例方法**

为该材质设置显式激活外观。

## 声明

```swift
func materialActiveAppearance(_ appearance: MaterialActiveAppearance) -> Material
```

## 讨论

在 macOS 上，用作容器背景的材质会在窗口处于非活动状态时自动显示为非活动状态，但可以通过将激活外观行为设置为“始终激活”来使其始终显示为活动状态：

```swift
Text("Hello, World!")
    .containerBackground(
        Material.regular.materialActiveAppearance(.active),
        for: .window)
```


---
source: https://developer.apple.com/documentation/SwiftUI/Material/materialActiveAppearance(_:)
crawled: 2025-12-03T04:53:48Z
---

# materialActiveAppearance(_:)

**Instance Method**

Sets an explicit active appearance for this material.

## Declaration

```swift
func materialActiveAppearance(_ appearance: MaterialActiveAppearance) -> Material
```

## Discussion

Materials used as the `window` container background on macOS will automatically appear inactive when their the window appears inactive, but can be made to always appear active by setting the active appearance behavior to be always active:

```swift
Text("Hello, World!")
    .containerBackground(
        Material.regular.materialActiveAppearance(.active),
        for: .window)
```

