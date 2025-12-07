--- 来源：https://developer.apple.com/documentation/SwiftUI/View/transaction(value:_:)

抓取时间：2025-12-02T17:34:32Z

---

# transaction(value:_:)

**实例方法**

将给定的事务变更函数应用于视图中使用的所有动画。

## 声明

```swift
nonisolated func transaction(value: some Equatable, _ transform: @escaping (inout Transaction) -> Void) -> some View

```

## 参数

- **value**：要监视其变化的值。

- **transform**：要应用于此视图中事务的转换。

## 返回值

一个包装此视图的视图，当 `value` 发生变化时，该视图会将转换应用于视图中使用的所有事务。

## 说明

使用此修饰符可以更改或替换视图中使用的动画。假设有三个相同的视图，它们由一个按钮控制，该按钮可以同时更改这三个视图：

- 第一个视图使“旋转”视图（[Text](../Text.zh-Hans.md)）旋转 360 度。

- 第二个视图使用修改器（`transaction(_:)`）更改动画，方法是将动画开始时间延迟两秒，然后将“旋转修改”视图（[Text](../Text.zh-Hans.md)）的旋转速度提高 2 倍。

- 第三个视图使用修改器（`transaction(_:)`）禁用影响“动画替换”视图（[Text](../Text.zh-Hans.md)）的动画。

以下代码实现了这些动画：

```swift
struct TransactionExample: View {
    @State var flag = false

    var body: some View {
        VStack(spacing: 50) {
            HStack(spacing: 30) {
                Text("Rotation")
                    .rotationEffect(Angle(degrees: flag ? 360 : 0))

                Text("Rotation\nModified")
                    .rotationEffect(Angle(degrees: flag ? 360 : 0))
                    .transaction(value: flag) { t in
                        t.animation =
                            t.animation?.delay(2.0).speed(2)
                    }

                Text("Animation\nReplaced")
                    .rotationEffect(Angle(degrees: flag ? 360 : 0))
                    .transaction(value: flag) { t in
                        t.disableAnimations = true
                    }
            }

            Button("Animate") {
                withAnimation(.easeIn(duration: 2.0)) {
                    flag.toggle()
                }
            }
        }
    }
}
```

## 将动画移动到另一个视图

- **withTransaction(_:_:)**：使用指定的事务执行闭包并返回结果。

- **withTransaction(_:_:_:)**：使用指定的事务键路径和值执行闭包并返回结果。

- **transaction(_:)**：将给定的事务变更函数应用于视图中使用的所有动画。

- **transaction(_:body:)**：将给定的事务变更函数应用于 `body` 闭包中使用的所有动画。

- **Transaction**：当前状态处理更新的上下文。

- **Entry()**：创建环境值、事务、容器值或焦点值条目。

- **TransactionKey**：用于访问事务中值的键。


---
source: https://developer.apple.com/documentation/SwiftUI/View/transaction(value:_:)
crawled: 2025-12-02T17:34:32Z
---

# transaction(value:_:)

**Instance Method**

Applies the given transaction mutation function to all animations used within the view.

## Declaration

```swift
nonisolated func transaction(value: some Equatable, _ transform: @escaping (inout Transaction) -> Void) -> some View

```

## Parameters

- **value**: A value to monitor for changes.
- **transform**: The transformation to apply to transactions within this view.

## Return Value

A view that wraps this view and applies a transformation to all transactions used within the view whenever `value` changes.

## Discussion

Use this modifier to change or replace the animation used in a view. Consider three identical views controlled by a button that changes all three simultaneously:

- The first view animates rotating the “Rotation” [Text](../Text.zh-Hans.md) view by 360 degrees.
- The second uses the `transaction(_:)` modifier to change the animation by adding a delay to the start of the animation by two seconds and then increases the rotational speed of the “Rotation\nModified” [Text](../Text.zh-Hans.md) view animation by a factor of 2.
- The third uses the `transaction(_:)` modifier to disable animations affecting the “Animation\nReplaced” [Text](../Text.zh-Hans.md) view.

The following code implements these animations:

```swift
struct TransactionExample: View {
    @State var flag = false

    var body: some View {
        VStack(spacing: 50) {
            HStack(spacing: 30) {
                Text("Rotation")
                    .rotationEffect(Angle(degrees: flag ? 360 : 0))

                Text("Rotation\nModified")
                    .rotationEffect(Angle(degrees: flag ? 360 : 0))
                    .transaction(value: flag) { t in
                        t.animation =
                            t.animation?.delay(2.0).speed(2)
                    }

                Text("Animation\nReplaced")
                    .rotationEffect(Angle(degrees: flag ? 360 : 0))
                    .transaction(value: flag) { t in
                        t.disableAnimations = true
                    }
            }

            Button("Animate") {
                withAnimation(.easeIn(duration: 2.0)) {
                    flag.toggle()
                }
            }
        }
    }
}
```

## Moving an animation to another view

- **withTransaction(_:_:)**: Executes a closure with the specified transaction and returns the result.
- **withTransaction(_:_:_:)**: Executes a closure with the specified transaction key path and value and returns the result.
- **transaction(_:)**: Applies the given transaction mutation function to all animations used within the view.
- **transaction(_:body:)**: Applies the given transaction mutation function to all animations used within the `body` closure.
- **Transaction**: The context of the current state-processing update.
- **Entry()**: Creates an environment values, transaction, container values, or focused values entry.
- **TransactionKey**: A key for accessing values in a transaction.

