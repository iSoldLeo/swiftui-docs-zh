--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onImmersionChange(initial:_:)

抓取时间：2025-12-02T17:22:00Z

---

# onImmersionChange(initial:_:)

**实例方法**

当应用的沉浸状态改变时执行操作。

## 声明

```swift
nonisolated func onImmersionChange(initial: Bool = true, _ action: @escaping (ImmersionChangeContext, ImmersionChangeContext) -> Void) -> some View

```

## 参数

- **initial**：此视图首次出现时是否应运行此操作。

- **action**：沉浸状态改变时要运行的闭包。

## 讨论

根据应用中沉浸空间使用的沉浸样式，可以通过旋转数码表冠等操作来控制沉浸程度。使用此修饰符定义一个闭包，该闭包会在沉浸状态改变时运行。以下示例根据当前的沉浸程度设置绑定值：

```swift
struct ImmersiveView: View {
    @Binding var enableSoundEffects: Bool

    var body: some View {
        MyView()
            .onImmersionChange { _, newImmersion in
                guard let amount = newImmersion.amount else {
                    enableSoundEffects = false
                    return
                }
                // Enable some effects based on the updated
                // amount of immersion
                enableSoundEffects = amount > 0.5
            }
    }
}
```

## 响应沉浸状态变化

- **ImmersionChangeContext**：表示应用沉浸状态的结构体。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onImmersionChange(initial:_:)
crawled: 2025-12-02T17:22:00Z
---

# onImmersionChange(initial:_:)

**Instance Method**

Performs an action when the immersion state of your app changes.

## Declaration

```swift
nonisolated func onImmersionChange(initial: Bool = true, _ action: @escaping (ImmersionChangeContext, ImmersionChangeContext) -> Void) -> some View

```

## Parameters

- **initial**: Whether the action should be run when this view initially appears.
- **action**: A closure to run when the immersion changes.

## Discussion

Depending on the immersion style used for the Immersive Space in your app, the amount of immersion can be controlled by actions such as turning the Digital Crown. Use this modifier to define a closure that is run when the immersion state changes. The following example sets the value of a binding depending on the current amount of immersion:

```swift
struct ImmersiveView: View {
    @Binding var enableSoundEffects: Bool

    var body: some View {
        MyView()
            .onImmersionChange { _, newImmersion in
                guard let amount = newImmersion.amount else {
                    enableSoundEffects = false
                    return
                }
                // Enable some effects based on the updated
                // amount of immersion
                enableSoundEffects = amount > 0.5
            }
    }
}
```

## Responding to immersion changes

- **ImmersionChangeContext**: A structure that represents a state of immersion of your app.

