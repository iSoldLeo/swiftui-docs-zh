---
来源： https://developer.apple.com/documentation/SwiftUI/DropDelegate/validateDrop(info:)
抓取时间： 2025-12-03T06:47:10Z
---

# validateDrop(info:)

**实例方法**

告诉委托，包含符合预期类型之一的项目的下拉列表进入了接受下拉列表的视图。

## 声明

```swift
@MainActor @preconcurrency func validateDrop(info: DropInfo) -> Bool
```

## 讨论

在向视图应用下拉修改器时指定预期类型。默认实现返回`true`。

## 接收下拉信息

- **dropEntered(info:)**：告诉代表一个有效的下拉信息已进入修改过的视图。
- **dropExited(info:)**：告诉代表一个经过验证的下拉操作已退出修改后的视图。
- **dropUpdated(info:)**：告诉委托已在修改后的视图内移动了已验证的下拉操作。
- **performDrop(info:)**：告诉委托可以从给定的信息中请求项目提供者数据。


---
source: https://developer.apple.com/documentation/SwiftUI/DropDelegate/validateDrop(info:)
crawled: 2025-12-03T06:47:10Z
---

# validateDrop(info:)

**Instance Method**

Tells the delegate that a drop containing items conforming to one of the expected types entered a view that accepts drops.

## Declaration

```swift
@MainActor @preconcurrency func validateDrop(info: DropInfo) -> Bool
```

## Discussion

Specify the expected types when you apply the drop modifier to the view. The default implementation returns `true`.

## Receiving drop information

- **dropEntered(info:)**: Tells the delegate a validated drop has entered the modified view.
- **dropExited(info:)**: Tells the delegate a validated drop operation has exited the modified view.
- **dropUpdated(info:)**: Tells the delegate that a validated drop moved inside the modified view.
- **performDrop(info:)**: Tells the delegate it can request the item provider data from the given information.

