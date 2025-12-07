---
来源： https://developer.apple.com/documentation/SwiftUI/DropDelegate/performDrop(info:)
抓取时间： 2025-12-01T11:36:20Z
---

# performDrop(info:)

**实例方法**

告诉委托可以从给定的信息中请求项目提供者数据。

## 声明

```swift
@MainActor @preconcurrency func performDrop(info: DropInfo) -> Bool
```

## 返回值

布尔值，如果删除成功则返回 `true`，否则返回 `false`。

## 讨论

酌情将接收到的数据纳入应用程序的数据模型。

确保在本方法的范围内开始加载`NSItemProvider` 实例的内容。不要在不同的角色上异步执行加载。加载内容可以稍后完成，但必须从这里开始。出于安全原因，只有在本方法返回之前，丢弃接收者才能访问丢弃的有效载荷。

## 接收丢弃信息

- **dropEntered(info:)**：告诉委托人一个有效的丢弃已进入修改过的视图。
- **dropExited(info:)**：告诉代表一个经过验证的下拉操作已退出修改后的视图。
- **dropUpdated(info:)**：告诉委托已在修改后的视图内移动了已验证的下拉操作。
- **validateDrop(info:)**：告诉委托，包含符合预期类型之一的项目的 drop 进入了接受 drop 的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/DropDelegate/performDrop(info:)
crawled: 2025-12-01T11:36:20Z
---

# performDrop(info:)

**Instance Method**

Tells the delegate it can request the item provider data from the given information.

## Declaration

```swift
@MainActor @preconcurrency func performDrop(info: DropInfo) -> Bool
```

## Return Value

A Boolean that is `true` if the drop was successful, `false` otherwise.

## Discussion

Incorporate the received data into your app’s data model as appropriate.

Make sure to start loading the contents of `NSItemProvider` instances from [DropInfo](../DropInfo.zh-Hans.md) within the scope of this method. Do not perform loading asynchronously on a different actor. Loading the contents may finish later, but it must start here. For security reasons, the drop receiver can access the dropped payload only before this method returns.

## Receiving drop information

- **dropEntered(info:)**: Tells the delegate a validated drop has entered the modified view.
- **dropExited(info:)**: Tells the delegate a validated drop operation has exited the modified view.
- **dropUpdated(info:)**: Tells the delegate that a validated drop moved inside the modified view.
- **validateDrop(info:)**: Tells the delegate that a drop containing items conforming to one of the expected types entered a view that accepts drops.

