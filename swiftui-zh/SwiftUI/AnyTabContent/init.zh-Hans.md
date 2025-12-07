--- 来源：https://developer.apple.com/documentation/SwiftUI/AnyTabContent/init(_:)

抓取时间：2025-12-03T06:01:57Z

---

# init(_:)

**Initializer**

创建一个实例，该实例会擦除 `tabContent` 的类型。

## 声明

```swift
init<T>(_ tabContent: T) where SelectionValue == T.TabValue, T : TabContent
```


---
source: https://developer.apple.com/documentation/SwiftUI/AnyTabContent/init(_:)
crawled: 2025-12-03T06:01:57Z
---

# init(_:)

**Initializer**

Create an instance that type-erases `tabContent`.

## Declaration

```swift
init<T>(_ tabContent: T) where SelectionValue == T.TabValue, T : TabContent
```

