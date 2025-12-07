--- 来源：https://developer.apple.com/documentation/SwiftUI/ControlWidgetTemplate/tint(_:)

抓取时间：2025-12-01T10:55:21Z

---

# tint(_:)

**实例方法**

设置此控件模板中的色调颜色。

## 声明

```swift
@MainActor @preconcurrency func tint(_ tint: Color?) -> some ControlWidgetTemplate

```

## 参数

- **tint**：要应用的色调。

## 说明

控件在应用于控件标签时不会遵循修饰符，控件也不支持任意色调形状样式。要为控件定义色调颜色，请将以下修饰符应用于其模板：

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
            .tint(.orange)
        }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/ControlWidgetTemplate/tint(_:)
crawled: 2025-12-01T10:55:21Z
---

# tint(_:)

**Instance Method**

Sets the tint color within this control template.

## Declaration

```swift
@MainActor @preconcurrency func tint(_ tint: Color?) -> some ControlWidgetTemplate

```

## Parameters

- **tint**: The tint [Color](../Color.zh-Hans.md) to apply.

## Discussion

Controls don’t respect the [tint(_:)](../View/tint.zh-Hans.md) modifier when applied to control labels, nor do controls support arbitrary tint shape styles. Instead, define a tint color for your control by applying this modifier to its template:

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
            .tint(.orange)
        }
    }
}
```

