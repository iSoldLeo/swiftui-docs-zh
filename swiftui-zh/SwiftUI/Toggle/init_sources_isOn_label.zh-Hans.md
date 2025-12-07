---
来源：https://developer.apple.com/documentation/SwiftUI/Toggle/init(sources:isOn:label:)
抓取时间：2025-12-01T02:45:31Z
---

# init(sources:isOn:label:)

**Initializer**

创建一个切换按钮，代表带有自定义标签的值集合。

### 声明

```swift
init<C>(sources: C, isOn: KeyPath<C.Element, Binding<Bool>>, @ViewBuilder label: () -> Label) where C : RandomAccessCollection
```

## 参数

- **sources**：用于渲染 Toggle 状态的源值集合。
- **isOn**：决定切换是打开、混合还是关闭的值的关键路径。
- **label**：描述切换目的的视图。

### 讨论

下面的示例创建了代表多个警报状态的单个切换器：

```swift
struct Alarm: Hashable, Identifiable {
    var id = UUID()
    var isOn = false
    var name = ""
}

@State private var alarms = [
    Alarm(isOn: true, name: "Morning"),
    Alarm(isOn: false, name: "Evening")
]

Toggle(sources: $alarms, isOn: \.isOn) {
    Text("Enable all alarms")
}
```

## 为警报集合创建一个切换器

- **init(_:sources:isOn:)**：创建一个代表值集合的切换按钮，其标签由本地化的字符串键生成。
- **init(_:image:sources:isOn:)**：创建代表值集合的切换按钮，该值集合的标签由本地化字符串键和图像资源生成。
- **init(_:systemImage:sources:isOn:)**：创建一个切换按钮，代表一个通过本地化字符串键和系统图像生成标签的值集合。


---
source: https://developer.apple.com/documentation/SwiftUI/Toggle/init(sources:isOn:label:)
crawled: 2025-12-01T02:45:31Z
---

# init(sources:isOn:label:)

**Initializer**

Creates a toggle representing a collection of values with a custom label.

## Declaration

```swift
init<C>(sources: C, isOn: KeyPath<C.Element, Binding<Bool>>, @ViewBuilder label: () -> Label) where C : RandomAccessCollection
```

## Parameters

- **sources**: A collection of values used as the source for rendering the Toggle’s state.
- **isOn**: The key path of the values that determines whether the toggle is on, mixed or off.
- **label**: A view that describes the purpose of the toggle.

## Discussion

The following example creates a single toggle that represents the state of multiple alarms:

```swift
struct Alarm: Hashable, Identifiable {
    var id = UUID()
    var isOn = false
    var name = ""
}

@State private var alarms = [
    Alarm(isOn: true, name: "Morning"),
    Alarm(isOn: false, name: "Evening")
]

Toggle(sources: $alarms, isOn: \.isOn) {
    Text("Enable all alarms")
}
```

## Creating a toggle for a collection

- **init(_:sources:isOn:)**: Creates a toggle representing a collection of values that generates its label from a localized string key.
- **init(_:image:sources:isOn:)**: Creates a toggle representing a collection of values that generates its label from a localized string key and image resource.
- **init(_:systemImage:sources:isOn:)**: Creates a toggle representing a collection of values that generates its label from a localized string key and system image.

