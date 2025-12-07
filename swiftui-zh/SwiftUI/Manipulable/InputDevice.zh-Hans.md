---
来源： https://developer.apple.com/documentation/SwiftUI/Manipulable/InputDevice
抓取时间： 2025-12-02T17:48:01Z
---

# Manipulable.InputDevice

**Structure**

描述手或触控板等输入设备。

## 声明

```swift
struct InputDevice
```

## 实例属性

- **chirality**：该输入设备的手部手性（左或右），或 `nil` （如果该输入设备没有手部手性）。
- **kind**：该输入设备的种类。
- **pose**：该输入设备的姿态，如果该输入设备没有姿态，则为`nil`。

## 枚举

- **Manipulable.InputDevice.Chirality**：描述输入设备的手部手性（左或右）。
- **Manipulable.InputDevice.Kind**：描述输入设备的种类。

## 符合

- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/Manipulable/InputDevice
crawled: 2025-12-02T17:48:01Z
---

# Manipulable.InputDevice

**Structure**

Describes an input device like a hand or a trackpad.

## Declaration

```swift
struct InputDevice
```

## Instance Properties

- **chirality**: The hand chirality (left or right) of this input device, or `nil` if this input device has no hand chirality.
- **kind**: The kind of this input device.
- **pose**: The pose of this input device, or `nil` if this input device has no pose.

## Enumerations

- **Manipulable.InputDevice.Chirality**: Describes hand chirality (left or right) of an input device.
- **Manipulable.InputDevice.Kind**: Describes the kind of an input device.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

