---
来源： https://developer.apple.com/documentation/SwiftUI/ColumnsFormStyle/init()
抓取时间： 2025-12-04T13:13:36Z
---

# init()

**Initializer**

非滚动表单样式，尾部对齐的标签列紧邻前部对齐的数值列。

### 声明

```swift
init()
```

## 讨论

不要直接调用这个初始化程序。相反，请使用 [columns](../FormStyle/columns.zh-Hans.md) 静态变量来创建此样式：

```swift
Form {
   ...
}
.formStyle(.columns)
```


---
source: https://developer.apple.com/documentation/SwiftUI/ColumnsFormStyle/init()
crawled: 2025-12-04T13:13:36Z
---

# init()

**Initializer**

A non-scrolling form style with a trailing aligned column of labels next to a leading aligned column of values.

## Declaration

```swift
init()
```

## Discussion

Don’t call this initializer directly. Instead, use the [columns](../FormStyle/columns.zh-Hans.md) static variable to create this style:

```swift
Form {
   ...
}
.formStyle(.columns)
```

