---
来源： https://developer.apple.com/documentation/SwiftUI/DropDelegate/dropExited(info:)
抓取时间： 2025-12-01T11:36:18Z
---

# dropExited(info:)

**实例方法**

告诉委托一个有效的下拉操作已退出修改后的视图。

## 声明

```swift
@MainActor @preconcurrency func dropExited(info: DropInfo)
```

## 讨论

默认实现什么也不做。

## 接收下拉信息

- **dropEntered(info:)**：告诉代表一个有效的下拉信息已进入修改过的视图。
- **dropUpdated(info:)**：告诉代表一个经过验证的液滴已进入修改后的视图。
- **validateDrop(info:)**：告诉委托，包含符合预期类型之一的项目的 drop 进入了接受 drop 的视图。
- **performDrop(info:)**：告诉委托可以从给定的信息中请求项目提供者数据。


---
source: https://developer.apple.com/documentation/SwiftUI/DropDelegate/dropExited(info:)
crawled: 2025-12-01T11:36:18Z
---

# dropExited(info:)

**Instance Method**

Tells the delegate a validated drop operation has exited the modified view.

## Declaration

```swift
@MainActor @preconcurrency func dropExited(info: DropInfo)
```

## Discussion

The default implementation does nothing.

## Receiving drop information

- **dropEntered(info:)**: Tells the delegate a validated drop has entered the modified view.
- **dropUpdated(info:)**: Tells the delegate that a validated drop moved inside the modified view.
- **validateDrop(info:)**: Tells the delegate that a drop containing items conforming to one of the expected types entered a view that accepts drops.
- **performDrop(info:)**: Tells the delegate it can request the item provider data from the given information.

