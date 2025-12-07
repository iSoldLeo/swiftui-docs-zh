--- 来源：https://developer.apple.com/documentation/SwiftUI/Button/init(role:action:)

抓取时间：2025-12-02T21:48:10Z

---

# init(role:action:)

**Initializer**

创建一个显示默认标签的按钮。

## 声明

```swift
@preconcurrency init(role: ButtonRole, action: @escaping @MainActor () -> Void)
```

## 参数

- **role**：描述按钮的语义角色。

- **action**：用户触发按钮时要执行的操作。

## 说明

例如，以下视图将在工具栏中显示一个带有“x”符号的按钮。

struct NewContactSheet: View { var body: some View { NavigationStack { NewContactEditor() .toolbar { Button(role: .cancel) { dismissView() } } } } }


---
source: https://developer.apple.com/documentation/SwiftUI/Button/init(role:action:)
crawled: 2025-12-02T21:48:10Z
---

# init(role:action:)

**Initializer**

Creates a button that displays a default label.

## Declaration

```swift
@preconcurrency init(role: ButtonRole, action: @escaping @MainActor () -> Void)
```

## Parameters

- **role**: A semantic role describing the button.
- **action**: The action to perform when the user triggers the button.

## Discussion

For example, the following view would display a button with a ‘x’ symbol in the toolbar.

struct NewContactSheet: View { var body: some View { NavigationStack { NewContactEditor() .toolbar { Button(role: .cancel) { dismissView() } } } } }

