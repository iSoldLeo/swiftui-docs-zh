---
来源： https://developer.apple.com/documentation/SwiftUI/Manipulable/Event/Value-swift.struct
抓取时间： 2025-12-03T07:12:32Z
---

# Manipulable.Event.Value

**Structure**

描述与操作手势事件相关的值。

### 声明

```swift
struct Value
```

## 实例属性

- **frame**：被操作视图的 3D 边界框。
- **inputDevices**：人用来操作视图的输入设备。
- **interactionPoint**：人与视图交互并开始操作视图的时间点。
- **timestamp**：事件被处理的时间。
- **transform**：被操作视图的三维仿射变换，如果视图没有定义明确的三维仿射变换，则为`nil`。

## 符合

- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/Manipulable/Event/Value-swift.struct
crawled: 2025-12-03T07:12:32Z
---

# Manipulable.Event.Value

**Structure**

Describes the value associated with a manipulation gesture event.

## Declaration

```swift
struct Value
```

## Instance Properties

- **frame**: The 3D bounding box of the manipulated view.
- **inputDevices**: The input devices that a person is using to manipulate a view.
- **interactionPoint**: The point at which a person interacted with a view to begin manipulating it.
- **timestamp**: The time the event was processed.
- **transform**: The 3D affine transform of the manipulated view, or `nil` if the view doesn’t have a well-defined 3D affine transfrorm.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

