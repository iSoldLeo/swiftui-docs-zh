---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/purchase
抓取时间： 2025-12-03T06:07:12Z
---

# 购买

**实例属性**

启动应用内购买的操作。

## 声明

```swift
@MainActor @preconcurrency var purchase: PurchaseAction { get }
```

## 讨论

读取此环境值可获取给定[Environment](../Environment.zh-Hans.md)的`PurchaseAction`实例。调用该实例可启动应用内购买。您直接调用该实例是因为它定义了一个 `PurchaseAction/callAsFunction(_:options:)` 方法，当您调用该实例时，Swift 会调用该方法。

例如，您可以在用户点击按钮时启动应用内购买：

```swift
struct PurchaseExample: View {
    @Environment(\.purchase) private var purchase
    let product: Product
    let purchaseOptions: [Product.PurchaseOption]

    var body: some View {
        Button {
            Task {
                let purchaseResult = try? await purchase(product, options: purchaseOptions)
                // Process purchase result.
            }
        } label: {
            Text(product.displayName)
        }
    }
}
```

## 操作

- **dismiss**：解除当前演示的操作。
- **dismissSearch**：结束当前搜索交互的操作。
- **dismissWindow**：存储在视图环境中的窗口关闭操作。
- **openImmersiveSpace**：呈现沉浸式空间的操作。
- **dismissImmersiveSpace**：存储在视图环境中的沉浸式空间取消动作。
- **newDocument**：环境中显示新文档的操作。
- **openDocument**：环境中显示现有文档的操作。
- **openURL**：打开 URL 的操作。
- **openWindow**：存储在视图环境中的窗口演示操作。
- **pushWindow**：存储在视图环境中的窗口演示操作。
- **refresh**：存储在视图环境中的刷新操作。
- **rename**：激活标准重命名交互的操作。
- **resetFocus**：请求焦点系统重新评估默认焦点的操作。
- **openSettings**：存储在视图环境中的设置演示操作。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/purchase
crawled: 2025-12-03T06:07:12Z
---

# purchase

**Instance Property**

An action that starts an in-app purchase.

## Declaration

```swift
@MainActor @preconcurrency var purchase: PurchaseAction { get }
```

## Discussion

Read this environment value to get an `PurchaseAction` instance for a given [Environment](../Environment.zh-Hans.md). Call the instance to start an in-app purchase. You call the instance directly because it defines a `PurchaseAction/callAsFunction(_:options:)` method that Swift calls when you call the instance.

For example, you can start an in-app purchase when the user taps a button:

```swift
struct PurchaseExample: View {
    @Environment(\.purchase) private var purchase
    let product: Product
    let purchaseOptions: [Product.PurchaseOption]

    var body: some View {
        Button {
            Task {
                let purchaseResult = try? await purchase(product, options: purchaseOptions)
                // Process purchase result.
            }
        } label: {
            Text(product.displayName)
        }
    }
}
```

## Actions

- **dismiss**: An action that dismisses the current presentation.
- **dismissSearch**: An action that ends the current search interaction.
- **dismissWindow**: A window dismissal action stored in a view’s environment.
- **openImmersiveSpace**: An action that presents an immersive space.
- **dismissImmersiveSpace**: An immersive space dismissal action stored in a view’s environment.
- **newDocument**: An action in the environment that presents a new document.
- **openDocument**: An action in the environment that presents an existing document.
- **openURL**: An action that opens a URL.
- **openWindow**: A window presentation action stored in a view’s environment.
- **pushWindow**: A window presentation action stored in a view’s environment.
- **refresh**: A refresh action stored in a view’s environment.
- **rename**: An action that activates the standard rename interaction.
- **resetFocus**: An action that requests the focus system to reevaluate default focus.
- **openSettings**: A Settings presentation action stored in a view’s environment.

