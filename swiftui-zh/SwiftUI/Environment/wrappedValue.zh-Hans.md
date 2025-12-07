--- 来源：https://developer.apple.com/documentation/SwiftUI/Environment/wrappedValue
抓取时间：2025-12-03T06:07:03Z

---

# wrappedValue

**实例属性**

环境属性的当前值。

## 声明

```swift
var wrappedValue: Value { get }
```

## 说明

wrappedValue 属性提供对值数据的主要访问。但是，您不能直接访问 `wrappedValue`。相反，您需要读取使用 [Environment](../Environment.zh-Hans.md) 属性包装器创建的属性变量：

```swift
@Environment(\.colorScheme) var colorScheme: ColorScheme

var body: some View {
    if colorScheme == .dark {
        DarkContent()
    } else {
        LightContent()
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/Environment/wrappedValue
crawled: 2025-12-03T06:07:03Z
---

# wrappedValue

**Instance Property**

The current value of the environment property.

## Declaration

```swift
var wrappedValue: Value { get }
```

## Discussion

The wrapped value property provides primary access to the value’s data. However, you don’t access `wrappedValue` directly. Instead, you read the property variable created with the [Environment](../Environment.zh-Hans.md) property wrapper:

```swift
@Environment(\.colorScheme) var colorScheme: ColorScheme

var body: some View {
    if colorScheme == .dark {
        DarkContent()
    } else {
        LightContent()
    }
}
```

