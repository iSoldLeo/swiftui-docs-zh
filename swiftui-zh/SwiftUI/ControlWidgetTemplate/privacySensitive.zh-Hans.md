--- 来源：https://developer.apple.com/documentation/SwiftUI/ControlWidgetTemplate/privacySensitive(_:)

抓取时间：2025-12-01T10:55:20Z

---

# privacySensitive(_:)

**实例方法**

将控件模板标记为包含敏感的、私密的用户数据。

## 声明

```swift
@MainActor @preconcurrency func privacySensitive(_ sensitive: Bool = true) -> some ControlWidgetTemplate

```

## 参数

- **sensitive**：一个布尔值，用于确定此控件是否为敏感控件。

## 说明

当控件显示在锁定屏幕上且设备处于锁定状态时，系统会隐藏带有此修饰符的控件。

控件也会遵循应用于控件标签的 [privacySensitive(_:)](../View/privacySensitive.zh-Hans.md) 修饰符。但是，该修饰符只会隐藏控件的内容。要同时隐藏控件的内容和状态，请将以下修饰符应用于控件模板：

```swift
struct GarageDoorOpener: ControlWidget {
    var body: some ControlWidgetConfiguration {
        StaticControlConfiguration(...) {
            ControlWidgetToggle(...) {
                Label(
                    $0 ? "Open" : "Closed",
                    systemImage: $0 ? "door.open" : "door.closed"
                )
            }
            .privacySensitive()
        }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/ControlWidgetTemplate/privacySensitive(_:)
crawled: 2025-12-01T10:55:20Z
---

# privacySensitive(_:)

**Instance Method**

Marks the control template as containing sensitive, private user data.

## Declaration

```swift
@MainActor @preconcurrency func privacySensitive(_ sensitive: Bool = true) -> some ControlWidgetTemplate

```

## Parameters

- **sensitive**: A Boolean value that determines whether this control is sensitive.

## Discussion

The system redacts controls marked with this modifier when those controls are displayed on the Lock Screen and the device is locked.

Controls also respect the [privacySensitive(_:)](../View/privacySensitive.zh-Hans.md) modifier applied to the control’s label. That modifier only redacts the control content, however. To redact the content *and* the state of the control, apply this modifier to the control template:

```swift
struct GarageDoorOpener: ControlWidget {
    var body: some ControlWidgetConfiguration {
        StaticControlConfiguration(...) {
            ControlWidgetToggle(...) {
                Label(
                    $0 ? "Open" : "Closed",
                    systemImage: $0 ? "door.open" : "door.closed"
                )
            }
            .privacySensitive()
        }
    }
}
```

