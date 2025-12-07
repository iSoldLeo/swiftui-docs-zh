--- 来源：https://developer.apple.com/documentation/SwiftUI/WindowVisibilityToggle/init(windowID:)

抓取时间：2025-12-01T10:21:27Z

---

# init(windowID:)

**Initializer**

创建一个窗口可见性切换开关，用于更改特定窗口的可见性。

## 声明

```swift
init(windowID: String) where Label == DefaultWindowVisibilityToggleLabel
```

## 参数

- **windowID**：要切换的单例窗口类型的 `id`。如果此 ID 无效，则切换开关将被禁用且无法使用。


---
source: https://developer.apple.com/documentation/SwiftUI/WindowVisibilityToggle/init(windowID:)
crawled: 2025-12-01T10:21:27Z
---

# init(windowID:)

**Initializer**

Create a window visibility toggle to alter the visibility of a specific window.

## Declaration

```swift
init(windowID: String) where Label == DefaultWindowVisibilityToggleLabel
```

## Parameters

- **windowID**: The `id` of the singleton window type that should be toggled. If this is not a valid id, the toggle will be disabled and non-functional.

