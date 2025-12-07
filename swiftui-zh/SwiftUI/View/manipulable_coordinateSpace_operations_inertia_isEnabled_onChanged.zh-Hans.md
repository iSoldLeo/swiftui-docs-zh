--- 来源：https://developer.apple.com/documentation/SwiftUI/View/manipulable(coordinateSpace:operations:inertia:isEnabled:onChanged:)

抓取时间：2025-12-02T17:24:32Z

---

# manipulable(coordinateSpace:operations:inertia:isEnabled:onChanged:)

**实例方法**

允许使用常见的手势操作此视图。

## 声明

```swift
nonisolated func manipulable(coordinateSpace: some CoordinateSpaceProtocol = .local, operations: Manipulable.Operation.Set = .all, inertia: Manipulable.Inertia = .medium, isEnabled: Bool = true, onChanged: ((Manipulable.Event) -> Void)? = nil) -> some View

```

## 参数

- **coordinateSpace**：操作手势事件位置的坐标空间。

- **operations**：用户操作此视图时可执行的操作集。

- **inertia**：此视图的惯性，定义了其抵抗操作的程度。

- **isEnabled**：布尔值，指示此视图修饰符添加的操作手势是否已启用。

- **onChanged**：每次发生新的操作手势事件时要执行的操作。

## 返回值

可以使用常用手势操作的视图。

## 说明

当用户结束操作手势时，视图将恢复到手势开始前的初始状态。

```swift
Model3D(named: "ToyRocket")
    .manipulable()
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/manipulable(coordinateSpace:operations:inertia:isEnabled:onChanged:)
crawled: 2025-12-02T17:24:32Z
---

# manipulable(coordinateSpace:operations:inertia:isEnabled:onChanged:)

**Instance Method**

Allows this view to be manipulated using common hand gestures.

## Declaration

```swift
nonisolated func manipulable(coordinateSpace: some CoordinateSpaceProtocol = .local, operations: Manipulable.Operation.Set = .all, inertia: Manipulable.Inertia = .medium, isEnabled: Bool = true, onChanged: ((Manipulable.Event) -> Void)? = nil) -> some View

```

## Parameters

- **coordinateSpace**: The coordinate space of the manipulation gesture event locations.
- **operations**: The set of allowed operations that can be applied when a person manipulates this view.
- **inertia**: The inertia of this view that defines how much it resists being manipulated.
- **isEnabled**: The Boolean value that indicates whether the manipulation gesture added by this view modifier is enabled or not.
- **onChanged**: The action to perform with each new manipulation gesture event.

## Return Value

A view that can be manipulated using common hand gestures.

## Discussion

When a person ends the manipulation gesture, the view will return to its initial transform from before the gesture began.

```swift
Model3D(named: "ToyRocket")
    .manipulable()
```

