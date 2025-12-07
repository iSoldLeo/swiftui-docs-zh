---
来源： https://developer.apple.com/documentation/SwiftUI/ButtonToggleStyle/init()
抓取时间： 2025-12-04T13:11:28Z
---

# init()

**Initializer**

创建按钮切换样式。

## 声明

```swift
init()
```

## 讨论

不要直接调用这个初始化程序。相反，请使用 [button](../ToggleStyle/button.zh-Hans.md) 静态变量来创建此样式：

```swift
Toggle(isOn: $isFlagged) {
    Label("Flag", systemImage: "flag.fill")
}
.toggleStyle(.button)
```


---
source: https://developer.apple.com/documentation/SwiftUI/ButtonToggleStyle/init()
crawled: 2025-12-04T13:11:28Z
---

# init()

**Initializer**

Creates a button toggle style.

## Declaration

```swift
init()
```

## Discussion

Don’t call this initializer directly. Instead, use the [button](../ToggleStyle/button.zh-Hans.md) static variable to create this style:

```swift
Toggle(isOn: $isFlagged) {
    Label("Flag", systemImage: "flag.fill")
}
.toggleStyle(.button)
```

