---
来源：https://developer.apple.com/documentation/SwiftUI/NavigationStack/init(路径：root:)
抓取时间： 2025-12-02T21:53:27Z
---

# init(path:root:)

**Initializer**

创建一个导航堆栈，该堆栈具有您可以控制的同质导航状态。

## 声明

```swift
@MainActor @preconcurrency init(path: Binding<Data>, @ViewBuilder root: () -> Root) where Data : MutableCollection, Data : RandomAccessCollection, Data : RangeReplaceableCollection, Data.Element : Hashable
```

## 参数

- **path**：此堆栈导航状态的[Binding](../Binding.zh-Hans.md)。
- **root**：堆栈为空时显示的视图。

## 讨论

如果不需要访问导航状态，请使用 [init(root:)](init_root.zh-Hans.md)。


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationStack/init(path:root:)
crawled: 2025-12-02T21:53:27Z
---

# init(path:root:)

**Initializer**

Creates a navigation stack with homogeneous navigation state that you can control.

## Declaration

```swift
@MainActor @preconcurrency init(path: Binding<Data>, @ViewBuilder root: () -> Root) where Data : MutableCollection, Data : RandomAccessCollection, Data : RangeReplaceableCollection, Data.Element : Hashable
```

## Parameters

- **path**: A [Binding](../Binding.zh-Hans.md) to the navigation state for this stack.
- **root**: The view to display when the stack is empty.

## Discussion

If you don’t need access to the navigation state, use [init(root:)](init_root.zh-Hans.md).

