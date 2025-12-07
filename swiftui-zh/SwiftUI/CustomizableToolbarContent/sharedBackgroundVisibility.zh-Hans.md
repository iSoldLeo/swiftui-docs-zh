--- 来源：https://developer.apple.com/documentation/SwiftUI/CustomizableToolbarContent/sharedBackgroundVisibility(_:)

抓取时间：2025-12-03T06:04:55Z

---

# sharedBackgroundVisibility(_:)

**实例方法**

控制工具栏中项目的玻璃背景效果的可见性。在某些情况下，例如 iOS 的导航栏和 macOS 的窗口工具栏，工具栏项目会应用玻璃背景效果，该效果会与其他位于同一逻辑分组中的项目共享。

## 声明

```swift
nonisolated func sharedBackgroundVisibility(_ visibility: Visibility) -> some CustomizableToolbarContent

```

## 参数

- **visibility**：背景效果的可见性。

## 说明

此修饰符调整该效果的可见性。隐藏该效果会将项目放置在其自身的分组中。

```swift
ContentView()
    .toolbar(id: "main") {
        ToolbarItem(id: "build-status", placement: principal) {
            BuildStatus()
        }
        .sharedBackgroundVisibility(.hidden)
    }
```


---
source: https://developer.apple.com/documentation/SwiftUI/CustomizableToolbarContent/sharedBackgroundVisibility(_:)
crawled: 2025-12-03T06:04:55Z
---

# sharedBackgroundVisibility(_:)

**Instance Method**

Controls the visibility of the glass background effect on items in the toolbar. In certain contexts, such as the navigation bar on iOS and the window toolbar on macOS, toolbar items will be given a glass background effect that is shared with other items in the same logical grouping.

## Declaration

```swift
nonisolated func sharedBackgroundVisibility(_ visibility: Visibility) -> some CustomizableToolbarContent

```

## Parameters

- **visibility**: The visibility of the background effect.

## Discussion

This modifier adjusts the visibility of that effect. Hiding the effect will cause the item to be placed in its own grouping.

```swift
ContentView()
    .toolbar(id: "main") {
        ToolbarItem(id: "build-status", placement: principal) {
            BuildStatus()
        }
        .sharedBackgroundVisibility(.hidden)
    }
```

