--- 来源：https://developer.apple.com/documentation/swiftui/wkinterfaceobjectrepresentable/makewkinterfaceobject(context:)

抓取时间：2025-12-02T15:07:07Z

---

# makeWKInterfaceObject(context:)

**实例方法**

创建一个 WatchKit 接口对象并配置其初始状态。

## 声明

```swift
@MainActor @preconcurrency func makeWKInterfaceObject(context: Self.Context) -> Self.WKInterfaceObjectType
```

## 参数

- **context**：包含系统当前状态信息的上下文结构。

## 返回值

使用提供的信息配置的接口对象。

## 说明

您必须实现此方法并使用它来创建接口对象。使用应用程序的当前数据和 `context` 参数的内容来配置该对象。系统仅在首次创建接口对象时调用此方法一次。对于所有后续更新，系统将调用 [updateWKInterfaceObject(_:context:)](updatewkinterfaceobject___context.zh-Hans.md) 方法。

## 创建和更新接口对象

- **updateWKInterfaceObject(_:context:)**：将呈现的 WatchKit 接口对象（及其协调器）更新到最新配置。

- **WKInterfaceObjectRepresentable.Context**


---
source: https://developer.apple.com/documentation/swiftui/wkinterfaceobjectrepresentable/makewkinterfaceobject(context:)
crawled: 2025-12-02T15:07:07Z
---

# makeWKInterfaceObject(context:)

**Instance Method**

Creates a WatchKit interface object and configures its initial state.

## Declaration

```swift
@MainActor @preconcurrency func makeWKInterfaceObject(context: Self.Context) -> Self.WKInterfaceObjectType
```

## Parameters

- **context**: A context structure containing information about the current state of the system.

## Return Value

Your interface object configured with the provided information.

## Discussion

You must implement this method and use it to create your interface object. Configure the object using your app’s current data and contents of the `context` parameter. The system calls this method only once, when it creates your interface object for the first time. For all subsequent updates, the system calls the [updateWKInterfaceObject(_:context:)](updatewkinterfaceobject___context.zh-Hans.md) method.

## Creating and updating the interface object

- **updateWKInterfaceObject(_:context:)**: Updates the presented WatchKit interface object (and its coordinator) to the latest configuration.
- **WKInterfaceObjectRepresentable.Context**

