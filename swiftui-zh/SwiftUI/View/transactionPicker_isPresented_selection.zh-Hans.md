--- 来源：https://developer.apple.com/documentation/SwiftUI/View/transactionPicker(isPresented:selection:)

抓取时间：2025-11-30T21:11:21Z

---

# transactionPicker(isPresented:selection:)

**实例方法**

显示一个交易选择器，用于选择交易集合。

## 声明

```swift
@MainActor @preconcurrency func transactionPicker(isPresented: Binding<Bool>, selection: Binding<[Transaction]>) -> some View

```

## 参数

- **isPresented**：绑定是否显示交易选择器。

- **selection**：从交易选择器中选择的交易。


---
source: https://developer.apple.com/documentation/SwiftUI/View/transactionPicker(isPresented:selection:)
crawled: 2025-11-30T21:11:21Z
---

# transactionPicker(isPresented:selection:)

**Instance Method**

Presents a picker that selects a collection of transactions.

## Declaration

```swift
@MainActor @preconcurrency func transactionPicker(isPresented: Binding<Bool>, selection: Binding<[Transaction]>) -> some View

```

## Parameters

- **isPresented**: The binding to whether the transaction picker should be shown.
- **selection**: The selection of transactions from the transaction picker.

