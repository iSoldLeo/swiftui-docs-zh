--- 来源：https://developer.apple.com/documentation/SwiftUI/DefaultToggleStyle/init()

抓取时间：2025-12-04T13:11:27Z

---

# init()

**Initializer**

创建默认切换样式。

## 声明

```swift
init()
```

## 讨论

不要直接调用此初始化器。请使用静态变量 [automatic](../ToggleStyle/automatic.zh-Hans.md) 来创建此样式：

```swift
Toggle("Enhance Sound", isOn: $isEnhanced)
    .toggleStyle(.automatic)
```


---
source: https://developer.apple.com/documentation/SwiftUI/DefaultToggleStyle/init()
crawled: 2025-12-04T13:11:27Z
---

# init()

**Initializer**

Creates a default toggle style.

## Declaration

```swift
init()
```

## Discussion

Don’t call this initializer directly. Instead, use the [automatic](../ToggleStyle/automatic.zh-Hans.md) static variable to create this style:

```swift
Toggle("Enhance Sound", isOn: $isEnhanced)
    .toggleStyle(.automatic)
```

