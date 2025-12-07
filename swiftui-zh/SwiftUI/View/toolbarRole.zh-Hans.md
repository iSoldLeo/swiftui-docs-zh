--- 来源：https://developer.apple.com/documentation/SwiftUI/View/toolbarRole(_:)

抓取时间：2025-11-30T21:16:27Z

---

# toolbarRole(_:)

**实例方法**

配置工具栏内容的语义角色。

## 声明

```swift
nonisolated func toolbarRole(_ role: ToolbarRole) -> some View

```

## 参数

- **role**：工具栏的角色。

## 说明

使用此修饰符配置应用工具栏内容的语义角色。SwiftUI 在渲染应用工具栏内容时会使用此角色。

```swift
ContentView()
    .navigationTitle("Browser")
    .toolbarRole(.browser)
    .toolbar {
        ToolbarItem(placement: .primaryAction) {
            AddButton()
        }
     }
```

## 指定工具栏内容的角色

- **ToolbarRole**：工具栏内容的用途。


---
source: https://developer.apple.com/documentation/SwiftUI/View/toolbarRole(_:)
crawled: 2025-11-30T21:16:27Z
---

# toolbarRole(_:)

**Instance Method**

Configures the semantic role for the content populating the toolbar.

## Declaration

```swift
nonisolated func toolbarRole(_ role: ToolbarRole) -> some View

```

## Parameters

- **role**: The role of the toolbar.

## Discussion

Use this modifier to configure the semantic role for content populating your app’s toolbar. SwiftUI uses this role when rendering the content of your app’s toolbar.

```swift
ContentView()
    .navigationTitle("Browser")
    .toolbarRole(.browser)
    .toolbar {
        ToolbarItem(placement: .primaryAction) {
            AddButton()
        }
     }
```

## Specifying the role of toolbar content

- **ToolbarRole**: The purpose of content that populates the toolbar.

