--- 来源：https://developer.apple.com/documentation/SwiftUI/View/transaction(_:)

抓取时间：2025-12-02T17:34:31Z

---

# transaction(_:)

**实例方法**

将给定的事务变更函数应用于视图中使用的所有动画。

## 声明

```swift
nonisolated func transaction(_ transform: @escaping (inout Transaction) -> Void) -> some View

```

## 参数

- **transform**：要应用于此视图中事务的转换。

## 返回值

一个包装此视图并将转换应用于视图中使用的所有事务的视图。

## 说明

使用此修饰符可以更改或替换视图中使用的动画。考虑三个相同的动画，它们由一个按钮控制，该按钮可以同时执行这三个动画：

- 第一个动画将“旋转”视图[Text](../Text.zh-Hans.md)旋转360度。

- 第二个动画使用`transaction(_:)`修改器，将动画的开始时间延迟两秒，然后将“旋转修改”视图[Text](../Text.zh-Hans.md)的旋转速度提高2倍。

- 第三个动画使用`transaction(_:)`修改器，将“动画替换”视图[Text](../Text.zh-Hans.md)的旋转动画替换为弹簧动画。

以下代码实现了这些动画：

```swift
struct TransactionExample: View {
    @State private var flag = false

    var body: some View {
        VStack(spacing: 50) {
            HStack(spacing: 30) {
                Text("Rotation")
                    .rotationEffect(Angle(degrees:
                                            self.flag ? 360 : 0))

                Text("Rotation\nModified")
                    .rotationEffect(Angle(degrees:
                                            self.flag ? 360 : 0))
                    .transaction { view in
                        view.animation =
                            view.animation?.delay(2.0).speed(2)
                    }

                Text("Animation\nReplaced")
                    .rotationEffect(Angle(degrees:
                                            self.flag ? 360 : 0))
                    .transaction { view in
                        view.animation = .interactiveSpring(
                            response: 0.60,
                            dampingFraction: 0.20,
                            blendDuration: 0.25)
                    }
            }

            Button("Animate") {
                withAnimation(.easeIn(duration: 2.0)) {
                    self.flag.toggle()
                }
            }
        }
    }
}
```

请在叶视图（例如 [Image](../Image.zh-Hans.md) 或 [Button](../Button.zh-Hans.md)）上使用此修饰符，而不是在容器视图（例如 [VStack](../VStack.zh-Hans.md) 或 [HStack](../HStack.zh-Hans.md)）上使用此修饰符。此转换将应用于此视图内的所有子视图；在容器视图上调用 `transaction(_:)` 可能会导致执行范围无限扩大，具体取决于视图层次结构的深度。

## 将动画移动到另一个视图

- **withTransaction(_:_:)**：使用指定的事务执行闭包并返回结果。

- **withTransaction(_:_:_:)**：使用指定的事务键路径和值执行闭包并返回结果。

- **transaction(value:_:)**：将给定的事务变更函数应用于视图中使用的所有动画。

- **transaction(_:body:)**：将给定的事务变更函数应用于 `body` 闭包中使用的所有动画。

- **Transaction**：当前状态处理更新的上下文。

- **Entry()**：创建环境值、事务、容器值或焦点值条目。

- **TransactionKey**：用于访问事务中值的键。


---
source: https://developer.apple.com/documentation/SwiftUI/View/transaction(_:)
crawled: 2025-12-02T17:34:31Z
---

# transaction(_:)

**Instance Method**

Applies the given transaction mutation function to all animations used within the view.

## Declaration

```swift
nonisolated func transaction(_ transform: @escaping (inout Transaction) -> Void) -> some View

```

## Parameters

- **transform**: The transformation to apply to transactions within this view.

## Return Value

A view that wraps this view and applies a transformation to all transactions used within the view.

## Discussion

Use this modifier to change or replace the animation used in a view. Consider three identical animations controlled by a button that executes all three animations simultaneously:

- The first animation rotates the “Rotation” [Text](../Text.zh-Hans.md) view by 360 degrees.
- The second uses the `transaction(_:)` modifier to change the animation by adding a delay to the start of the animation by two seconds and then increases the rotational speed of the “Rotation\nModified” [Text](../Text.zh-Hans.md) view animation by a factor of 2.
- The third animation uses the `transaction(_:)` modifier to replace the rotation animation affecting the “Animation\nReplaced” [Text](../Text.zh-Hans.md) view with a spring animation.

The following code implements these animations:

```swift
struct TransactionExample: View {
    @State private var flag = false

    var body: some View {
        VStack(spacing: 50) {
            HStack(spacing: 30) {
                Text("Rotation")
                    .rotationEffect(Angle(degrees:
                                            self.flag ? 360 : 0))

                Text("Rotation\nModified")
                    .rotationEffect(Angle(degrees:
                                            self.flag ? 360 : 0))
                    .transaction { view in
                        view.animation =
                            view.animation?.delay(2.0).speed(2)
                    }

                Text("Animation\nReplaced")
                    .rotationEffect(Angle(degrees:
                                            self.flag ? 360 : 0))
                    .transaction { view in
                        view.animation = .interactiveSpring(
                            response: 0.60,
                            dampingFraction: 0.20,
                            blendDuration: 0.25)
                    }
            }

            Button("Animate") {
                withAnimation(.easeIn(duration: 2.0)) {
                    self.flag.toggle()
                }
            }
        }
    }
}
```

Use this modifier on leaf views such as [Image](../Image.zh-Hans.md) or [Button](../Button.zh-Hans.md) rather than container views such as [VStack](../VStack.zh-Hans.md) or [HStack](../HStack.zh-Hans.md). The transformation applies to all child views within this view; calling `transaction(_:)` on a container view can lead to unbounded scope of execution depending on the depth of the view hierarchy.

## Moving an animation to another view

- **withTransaction(_:_:)**: Executes a closure with the specified transaction and returns the result.
- **withTransaction(_:_:_:)**: Executes a closure with the specified transaction key path and value and returns the result.
- **transaction(value:_:)**: Applies the given transaction mutation function to all animations used within the view.
- **transaction(_:body:)**: Applies the given transaction mutation function to all animations used within the `body` closure.
- **Transaction**: The context of the current state-processing update.
- **Entry()**: Creates an environment values, transaction, container values, or focused values entry.
- **TransactionKey**: A key for accessing values in a transaction.

