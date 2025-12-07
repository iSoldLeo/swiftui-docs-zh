--- 来源：https://developer.apple.com/documentation/swiftui/compositorcontent/onimmersionchange(initial:_:)

抓取时间：2025-12-03T06:32:38Z

---

# onImmersionChange(initial:_:)

**实例方法**

当应用的沉浸状态发生变化时执行操作。

## 声明

```swift
nonisolated func onImmersionChange(initial: Bool = true, _ action: @escaping (ImmersionChangeContext, ImmersionChangeContext) -> Void) -> some CompositorContent

```

## 参数

- **initial**：此视图首次出现时是否应运行此操作。

- **action**：沉浸状态发生变化时要运行的闭包。

## 讨论

根据应用中沉浸空间使用的沉浸样式，可以通过旋转数码表冠等操作来控制沉浸程度。使用此修饰符可以定义一个在沉浸状态改变时运行的闭包。


---
source: https://developer.apple.com/documentation/swiftui/compositorcontent/onimmersionchange(initial:_:)
crawled: 2025-12-03T06:32:38Z
---

# onImmersionChange(initial:_:)

**Instance Method**

Performs an action when the immersion state of your app changes.

## Declaration

```swift
nonisolated func onImmersionChange(initial: Bool = true, _ action: @escaping (ImmersionChangeContext, ImmersionChangeContext) -> Void) -> some CompositorContent

```

## Parameters

- **initial**: Whether the action should be run when this view initially appears.
- **action**: A closure to run when the immersion changes.

## Discussion

Depending on the immersion style used for the Immersive Space in your app, the amount of immersion can be controlled by actions such as turning the Digital Crown. Use this modifier to define a closure that is run when the immersion state changes.

