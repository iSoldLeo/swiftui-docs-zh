--- 来源：https://developer.apple.com/documentation/SwiftUI/WKApplicationDelegateAdaptor/init(_:)

抓取时间：2025-12-01T10:20:00Z

---

# init(_:)

**Initializer**

使用 WatchKit 应用程序委托创建 `WKApplicationDelegateAdaptor`。

## 声明

```swift
@MainActor @preconcurrency init(_ delegateType: DelegateType.Type = DelegateType.self)
```

## 说明

框架将初始化提供的委托并管理其生命周期，并在执行完自身工作后，在适当的时候调用该委托。


---
source: https://developer.apple.com/documentation/SwiftUI/WKApplicationDelegateAdaptor/init(_:)
crawled: 2025-12-01T10:20:00Z
---

# init(_:)

**Initializer**

Creates an `WKApplicationDelegateAdaptor` using a WatchKit Application Delegate.

## Declaration

```swift
@MainActor @preconcurrency init(_ delegateType: DelegateType.Type = DelegateType.self)
```

## Discussion

The framework will initialize the provided delegate and manage its lifetime, calling out to it when appropriate after performing its own work.



