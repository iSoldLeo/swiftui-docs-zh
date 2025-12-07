--- 来源：https://developer.apple.com/documentation/SwiftUI/CheckboxToggleStyle/init()

抓取时间：2025-12-04T13:11:30Z

---

# init()

**Initializer**

创建复选框切换样式。

## 声明

```swift
init()
```

## 讨论

不要直接调用此初始化器。而是使用 [checkbox](../ToggleStyle/checkbox.zh-Hans.md) 静态变量来创建此样式：

```swift
Toggle("Close windows when quitting an app", isOn: $doesClose)
    .toggleStyle(.checkbox)
```


---
source: https://developer.apple.com/documentation/SwiftUI/CheckboxToggleStyle/init()
crawled: 2025-12-04T13:11:30Z
---

# init()

**Initializer**

Creates a checkbox toggle style.

## Declaration

```swift
init()
```

## Discussion

Don’t call this initializer directly. Instead, use the [checkbox](../ToggleStyle/checkbox.zh-Hans.md) static variable to create this style:

```swift
Toggle("Close windows when quitting an app", isOn: $doesClose)
    .toggleStyle(.checkbox)
```

