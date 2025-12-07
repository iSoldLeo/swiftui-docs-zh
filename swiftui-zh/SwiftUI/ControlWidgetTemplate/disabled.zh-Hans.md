--- 来源：https://developer.apple.com/documentation/SwiftUI/ControlWidgetTemplate/disabled(_:)

抓取时间：2025-12-01T10:55:20Z

---

# disabled(_:)

**实例方法**

确定用户是否可以与此控件交互。

## 声明

```swift
@MainActor @preconcurrency func disabled(_ disabled: Bool) -> some ControlWidgetTemplate

```

## 参数

- **disabled**：一个布尔值，用于确定用户是否可以与此控件交互。

## 说明

控件也会响应应用于控件标签的 [disabled(_:)](../View/disabled.zh-Hans.md) 修饰符。但是，该修饰符仅禁用标签。要完全禁用控件，请将以下修饰符应用于控件模板：

```swift
struct GarageDoorOpener: ControlWidget {
    var body: some ControlWidgetConfiguration {
        StaticControlConfiguration(
            kind: "com.myapp.garagedooropener",
            provider: DoorValueProvider()
        ) { door in
            ControlWidgetToggle(...) {
                Label(
                    $0 ? "Open" : "Closed",
                    systemImage: $0 ? "door.open" : "door.closed"
                )
            }
            .disabled(door.isSafetyLockEngaged)
        }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/ControlWidgetTemplate/disabled(_:)
crawled: 2025-12-01T10:55:20Z
---

# disabled(_:)

**Instance Method**

Determines whether people can interact with this control.

## Declaration

```swift
@MainActor @preconcurrency func disabled(_ disabled: Bool) -> some ControlWidgetTemplate

```

## Parameters

- **disabled**: A Boolean value that determines whether users can interact with this control.

## Discussion

Controls also respect the [disabled(_:)](../View/disabled.zh-Hans.md) modifier applied to the control’s label. That modifier only disables the label, however. To disable the control overall, apply this modifier to the control template:

```swift
struct GarageDoorOpener: ControlWidget {
    var body: some ControlWidgetConfiguration {
        StaticControlConfiguration(
            kind: "com.myapp.garagedooropener",
            provider: DoorValueProvider()
        ) { door in
            ControlWidgetToggle(...) {
                Label(
                    $0 ? "Open" : "Closed",
                    systemImage: $0 ? "door.open" : "door.closed"
                )
            }
            .disabled(door.isSafetyLockEngaged)
        }
    }
}
```

