--- 来源：https://developer.apple.com/documentation/SwiftUI/View/manipulationGesture(updating:coordinateSpace:operations:inertia:isEnabled:onChanged:)

抓取时间：2025-12-02T17:24:34Z

---

# manipulationGesture(updating:coordinateSpace:operations:inertia:isEnabled:onChanged:)

**实例方法**

向此视图添加一个操作手势，但此视图本身不可操作。

## 声明

```swift
nonisolated func manipulationGesture(updating gestureState: Binding<Manipulable.GestureState>, coordinateSpace: some CoordinateSpaceProtocol = .local, operations: Manipulable.Operation.Set = .all, inertia: Manipulable.Inertia = .medium, isEnabled: Bool = true, onChanged: ((Manipulable.Event) -> Void)? = nil) -> some View

```

## 参数

- **gestureState**：操作手势要更新的状态。

- **coordinateSpace**：操作手势事件位置的坐标空间。

- **operations**：用户操作此视图时可执行的操作集合。

- **inertia**：此视图的惯性，定义了其抵抗操作的程度。

- **isEnabled**：布尔值，指示此视图修饰符添加的操作手势是否已启用。

- **onChanged**：每次发生新的操作手势事件时要执行的操作。

## 返回值

附加了操作手势但自身不可操作的视图。

## 说明

当您希望允许用户通过与另一个视图交互来操作当前视图时，请将此视图修饰符与 [manipulable(using:)](manipulable_using.zh-Hans.md) 一起使用。

在以下示例中，一个人可以做出一个与一副扑克牌相关的操控手势，该手势可以操控单张牌，而不是整副牌：

```swift
struct CardDeck: View {
    @State private var manipulationState = Manipulable.GestureState()

    var body: some View {
        ZStack {
            Model3D(named: "CardDeck")
                .manipulationGesture(updating: $manipulationState)
            Model3D(named: "Card")
                .manipulable(using: manipulationState)
                .opacity(manipulationState.isActive ? 1 : 0)
        }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/manipulationGesture(updating:coordinateSpace:operations:inertia:isEnabled:onChanged:)
crawled: 2025-12-02T17:24:34Z
---

# manipulationGesture(updating:coordinateSpace:operations:inertia:isEnabled:onChanged:)

**Instance Method**

Adds a manipulation gesture to this view without allowing this view to be manipulable itself.

## Declaration

```swift
nonisolated func manipulationGesture(updating gestureState: Binding<Manipulable.GestureState>, coordinateSpace: some CoordinateSpaceProtocol = .local, operations: Manipulable.Operation.Set = .all, inertia: Manipulable.Inertia = .medium, isEnabled: Bool = true, onChanged: ((Manipulable.Event) -> Void)? = nil) -> some View

```

## Parameters

- **gestureState**: The state that the manipulation gesture updates.
- **coordinateSpace**: The coordinate space of the manipulation gesture event locations.
- **operations**: The set of allowed operations that can be applied when a person manipulates this view.
- **inertia**: The inertia of this view that defines how much it resists being manipulated.
- **isEnabled**: The Boolean value that indicates whether the manipulation gesture added by this view modifier is enabled or not.
- **onChanged**: The action to perform with each new manipulation gesture event.

## Return Value

A view with a manipulation gesture attached but that isn’t manipulable itself.

## Discussion

Use this view modifier alongside [manipulable(using:)](manipulable_using.zh-Hans.md) when you want to allow a person to manipulate a view by interacting with a different view.

In the following example, a person can begin a manipulation gesture attached to a deck of cards which, in turn, manipulates a single card instead of the entire deck:

```swift
struct CardDeck: View {
    @State private var manipulationState = Manipulable.GestureState()

    var body: some View {
        ZStack {
            Model3D(named: "CardDeck")
                .manipulationGesture(updating: $manipulationState)
            Model3D(named: "Card")
                .manipulable(using: manipulationState)
                .opacity(manipulationState.isActive ? 1 : 0)
        }
    }
}
```



