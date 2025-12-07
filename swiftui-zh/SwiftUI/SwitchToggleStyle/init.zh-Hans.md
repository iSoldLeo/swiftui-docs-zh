--- 来源：https://developer.apple.com/documentation/SwiftUI/SwitchToggleStyle/init()

抓取时间：2025-12-04T13:11:32Z

---

# init()

**Initializer**

创建一个开关切换样式。

## 声明

```swift
init()
```

## 讨论

不要直接调用此初始化器。而是使用 [switch](../ToggleStyle/switch.zh-Hans.md) 静态变量来创建此样式：

```swift
Toggle("Enhance Sound", isOn: $isEnhanced)
    .toggleStyle(.switch)
```


---
source: https://developer.apple.com/documentation/SwiftUI/SwitchToggleStyle/init()
crawled: 2025-12-04T13:11:32Z
---

# init()

**Initializer**

Creates a switch toggle style.

## Declaration

```swift
init()
```

## Discussion

Don’t call this initializer directly. Instead, use the [switch](../ToggleStyle/switch.zh-Hans.md) static variable to create this style:

```swift
Toggle("Enhance Sound", isOn: $isEnhanced)
    .toggleStyle(.switch)
```

