---
来源： https://developer.apple.com/documentation/SwiftUI/WKApplicationDelegateAdaptor
抓取时间： 2025-12-02T17:20:40Z
---

# WKApplicationDelegateAdaptor

**Structure**

在 `App` 中使用的属性包装器，用于提供来自 WatchKit 的委托。

### 声明

```swift
@MainActor @preconcurrency @propertyWrapper struct WKApplicationDelegateAdaptor<DelegateType> where DelegateType : NSObject, DelegateType : WKApplicationDelegate
```

## 创建委托适配器

- **init(_:)**：使用 WatchKit 应用程序代理创建`WKApplicationDelegateAdaptor`。

## 获取委托适配器

- **projectedValue**：被观察对象的投影，使用动态成员查找功能为其属性创建绑定。
- **wrappedValue**：底层委托。

## targeting watchOS

- **WKExtensionDelegateAdaptor**：用于创建 WatchKit 扩展委托的属性包装器类型。

## 符合

- 动态属性
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/WKApplicationDelegateAdaptor
crawled: 2025-12-02T17:20:40Z
---

# WKApplicationDelegateAdaptor

**Structure**

A property wrapper that is used in `App` to provide a delegate from WatchKit.

## Declaration

```swift
@MainActor @preconcurrency @propertyWrapper struct WKApplicationDelegateAdaptor<DelegateType> where DelegateType : NSObject, DelegateType : WKApplicationDelegate
```

## Creating a delegate adaptor

- **init(_:)**: Creates an `WKApplicationDelegateAdaptor` using a WatchKit Application Delegate.

## Getting the delegate adaptor

- **projectedValue**: A projection of the observed object that creates bindings to its properties using dynamic member lookup.
- **wrappedValue**: The underlying delegate.

## Targeting watchOS

- **WKExtensionDelegateAdaptor**: A property wrapper type that you use to create a WatchKit extension delegate.

## Conforms To

- DynamicProperty
- Sendable
- SendableMetatype

