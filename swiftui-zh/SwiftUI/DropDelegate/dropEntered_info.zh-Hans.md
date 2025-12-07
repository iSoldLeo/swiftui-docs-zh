---
来源：https://developer.apple.com/documentation/SwiftUI/DropDelegate/dropEntered(info:)
抓取时间： 2025-12-01T11:36:17Z
---

# dropEntered(info:)

**实例方法**

告诉委托一个有效的 drop 已进入修改后的视图。

## 声明

```swift
@MainActor @preconcurrency func dropEntered(info: DropInfo)
```

## 讨论

默认实现什么也不做。

## 接收下拉信息

- **dropExited(info:)**：告诉委托一个有效的下拉操作已退出修改过的视图。
- **dropUpdated(info:)**：告诉委托已在修改后的视图内移动了已验证的下拉操作。
- **validateDrop(info:)**：告诉委托，包含符合预期类型之一的项目的 drop 进入了接受 drop 的视图。
- **performDrop(info:)**：告诉委托可以从给定的信息中请求项目提供者数据。


---
source: https://developer.apple.com/documentation/SwiftUI/DropDelegate/dropEntered(info:)
crawled: 2025-12-01T11:36:17Z
---

# dropEntered(info:)

**Instance Method**

Tells the delegate a validated drop has entered the modified view.

## Declaration

```swift
@MainActor @preconcurrency func dropEntered(info: DropInfo)
```

## Discussion

The default implementation does nothing.

## Receiving drop information

- **dropExited(info:)**: Tells the delegate a validated drop operation has exited the modified view.
- **dropUpdated(info:)**: Tells the delegate that a validated drop moved inside the modified view.
- **validateDrop(info:)**: Tells the delegate that a drop containing items conforming to one of the expected types entered a view that accepts drops.
- **performDrop(info:)**: Tells the delegate it can request the item provider data from the given information.

