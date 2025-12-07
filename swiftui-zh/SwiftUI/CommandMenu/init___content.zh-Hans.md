---
来源： https://developer.apple.com/documentation/SwiftUI/CommandMenu/init(_:content:)
抓取时间： 2025-12-01T11:11:32Z
---

# init(_:content:)

**Initializer**

创建一个新菜单，为一系列应用程序特定命令创建本地化名称，并插入到应用程序菜单的标准位置（位于 "视图 "菜单之后，与其他未注明位置的菜单依次排列）。

### 声明

```swift
init(_ name: LocalizedStringResource, @ViewBuilder content: () -> Content)
```


---
source: https://developer.apple.com/documentation/SwiftUI/CommandMenu/init(_:content:)
crawled: 2025-12-01T11:11:32Z
---

# init(_:content:)

**Initializer**

Creates a new menu with a localized name for a collection of app- specific commands, inserted in the standard location for app menus (after the View menu, in order with other menus declared without an explicit location).

## Declaration

```swift
init(_ name: LocalizedStringResource, @ViewBuilder content: () -> Content)
```

