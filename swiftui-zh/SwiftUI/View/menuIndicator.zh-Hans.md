--- 来源：https://developer.apple.com/documentation/SwiftUI/View/menuIndicator(_:)

抓取时间：2025-12-02T17:32:37Z

---

# menuIndicator(_:)

**实例方法**

设置此视图中控件的菜单指示器可见性。

## 声明

```swift
nonisolated func menuIndicator(_ visibility: Visibility) -> some View

```

## 参数

- **visibility**：要应用的菜单指示器可见性。

## 说明

使用此修饰符可以覆盖此视图中控件的默认菜单指示器可见性。例如，以下代码创建了一个没有指示器的菜单：

```swift
Menu {
    ForEach(history , id: \.self) { historyItem in
        Button(historyItem.title) {
            self.openURL(historyItem.url)
        }
    }
} label: {
    Label("Back", systemImage: "chevron.backward")
        .labelStyle(.iconOnly)
} primaryAction: {
    if let last = history.last {
        self.openURL(last.url)
    }
}
.menuIndicator(.hidden)
```

## 显示菜单指示器

- **menuIndicatorVisibility**：要应用于视图中控件的菜单指示器可见性。


---
source: https://developer.apple.com/documentation/SwiftUI/View/menuIndicator(_:)
crawled: 2025-12-02T17:32:37Z
---

# menuIndicator(_:)

**Instance Method**

Sets the menu indicator visibility for controls within this view.

## Declaration

```swift
nonisolated func menuIndicator(_ visibility: Visibility) -> some View

```

## Parameters

- **visibility**: The menu indicator visibility to apply.

## Discussion

Use this modifier to override the default menu indicator visibility for controls in this view. For example, the code below creates a menu without an indicator:

```swift
Menu {
    ForEach(history , id: \.self) { historyItem in
        Button(historyItem.title) {
            self.openURL(historyItem.url)
        }
    }
} label: {
    Label("Back", systemImage: "chevron.backward")
        .labelStyle(.iconOnly)
} primaryAction: {
    if let last = history.last {
        self.openURL(last.url)
    }
}
.menuIndicator(.hidden)
```



## Showing a menu indicator

- **menuIndicatorVisibility**: The menu indicator visibility to apply to controls within a view.

