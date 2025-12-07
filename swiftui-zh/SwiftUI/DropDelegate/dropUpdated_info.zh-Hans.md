---
来源： https://developer.apple.com/documentation/SwiftUI/DropDelegate/dropUpdated(info:)
抓取时间： 2025-12-01T11:36:18Z
---

# dropUpdated(info:)

**实例方法**

告诉委托已在修改后的视图中移动了已验证的 drop。

## 声明

```swift
@MainActor @preconcurrency func dropUpdated(info: DropInfo) -> DropProposal?
```

## 讨论

使用此方法返回包含委托人打算在丢弃点 [location](../DropInfo/location.zh-Hans.md) 执行的操作的丢弃建议。此方法的默认实现返回 `nil`，告诉丢弃使用最后返回的有效值，否则返回 [copy](../DropOperation/copy.zh-Hans.md)。

## 接收下拉信息

- **dropEntered(info:)**：告诉代表一个有效的下拉信息已进入修改过的视图。
- **dropExited(info:)**：告诉代表一个经过验证的下拉操作已退出修改后的视图。
- **validateDrop(info:)**：告诉委托，包含符合预期类型之一的项目的下拉操作进入了接受下拉操作的视图。
- **performDrop(info:)**：告诉委托可以从给定的信息中请求项目提供者数据。


---
source: https://developer.apple.com/documentation/SwiftUI/DropDelegate/dropUpdated(info:)
crawled: 2025-12-01T11:36:18Z
---

# dropUpdated(info:)

**Instance Method**

Tells the delegate that a validated drop moved inside the modified view.

## Declaration

```swift
@MainActor @preconcurrency func dropUpdated(info: DropInfo) -> DropProposal?
```

## Discussion

Use this method to return a drop proposal containing the operation the delegate intends to perform at the drop [location](../DropInfo/location.zh-Hans.md). The default implementation of this method returns `nil`, which tells the drop to use the last valid returned value or else [copy](../DropOperation/copy.zh-Hans.md).

## Receiving drop information

- **dropEntered(info:)**: Tells the delegate a validated drop has entered the modified view.
- **dropExited(info:)**: Tells the delegate a validated drop operation has exited the modified view.
- **validateDrop(info:)**: Tells the delegate that a drop containing items conforming to one of the expected types entered a view that accepts drops.
- **performDrop(info:)**: Tells the delegate it can request the item provider data from the given information.

