---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/init()
抓取时间： 2025-12-01T10:56:05Z
---

# init()

**Initializer**

创建环境值实例。

## 声明

```swift
init()
```

## 讨论

通常不会直接创建[EnvironmentValues](../EnvironmentValues.zh-Hans.md) 的实例。这样做只能访问不会根据系统设置或设备特性更新的默认值。相反，当您使用[Environment](../Environment.zh-Hans.md) 属性包装器和[environment(_:_:)](../View/environment.zh-Hans.md) 视图修饰符时，您将依赖 SwiftUI 为您管理的环境值实例。

## 创建和访问值

- **subscript(_:)**：访问与自定义键关联的环境值。
- **description**：表示环境值实例内容的字符串。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/init()
crawled: 2025-12-01T10:56:05Z
---

# init()

**Initializer**

Creates an environment values instance.

## Declaration

```swift
init()
```

## Discussion

You don’t typically create an instance of [EnvironmentValues](../EnvironmentValues.zh-Hans.md) directly. Doing so would provide access only to default values that don’t update based on system settings or device characteristics. Instead, you rely on an environment values’ instance that SwiftUI manages for you when you use the [Environment](../Environment.zh-Hans.md) property wrapper and the [environment(_:_:)](../View/environment.zh-Hans.md) view modifier.

## Creating and accessing values

- **subscript(_:)**: Accesses the environment value associated with a custom key.
- **description**: A string that represents the contents of the environment values instance.

