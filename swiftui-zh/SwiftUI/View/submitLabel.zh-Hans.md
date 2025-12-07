--- 来源：https://developer.apple.com/documentation/SwiftUI/View/submitLabel(_:)

抓取时间：2025-11-30T21:27:15Z

---

# submitLabel(_:)

**实例方法**

设置此视图的提交标签。

## 声明

```swift
nonisolated func submitLabel(_ submitLabel: SubmitLabel) -> some View

```

## 参数

- **submitLabel**：[SubmitLabel](../SubmitLabel.zh-Hans.md) 中指定的条件之一。

## 讨论

```swift
Form {
    TextField("Username", $viewModel.username)
        .submitLabel(.continue)
    SecureField("Password", $viewModel.password)
        .submitLabel(.done)
}
```

## 标记提交事件

- **SubmitLabel**：描述视图层次结构中提交标签的语义标签。


---
source: https://developer.apple.com/documentation/SwiftUI/View/submitLabel(_:)
crawled: 2025-11-30T21:27:15Z
---

# submitLabel(_:)

**Instance Method**

Sets the submit label for this view.

## Declaration

```swift
nonisolated func submitLabel(_ submitLabel: SubmitLabel) -> some View

```

## Parameters

- **submitLabel**: One of the cases specified in [SubmitLabel](../SubmitLabel.zh-Hans.md).

## Discussion

```swift
Form {
    TextField("Username", $viewModel.username)
        .submitLabel(.continue)
    SecureField("Password", $viewModel.password)
        .submitLabel(.done)
}
```

## Labeling a submission event

- **SubmitLabel**: A semantic label describing the label of submission within a view hierarchy.

