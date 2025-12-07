---
来源： https://developer.apple.com/documentation/SwiftUI/GroupedFormStyle/init()
抓取时间： 2025-12-04T13:13:37Z
---

# init()

**Initializer**

创建具有滚动分组行的表单样式。

### 声明

```swift
init()
```

## 讨论

不要直接调用这个初始化程序。相反，请使用 [grouped](../FormStyle/grouped.zh-Hans.md) 静态变量来创建此样式：

```swift
Form {
   ...
}
.formStyle(.grouped)
```


---
source: https://developer.apple.com/documentation/SwiftUI/GroupedFormStyle/init()
crawled: 2025-12-04T13:13:37Z
---

# init()

**Initializer**

Creates a form style with scrolling, grouped rows.

## Declaration

```swift
init()
```

## Discussion

Don’t call this initializer directly. Instead, use the [grouped](../FormStyle/grouped.zh-Hans.md) static variable to create this style:

```swift
Form {
   ...
}
.formStyle(.grouped)
```

