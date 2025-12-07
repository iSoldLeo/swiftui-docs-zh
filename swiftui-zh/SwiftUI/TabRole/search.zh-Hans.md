---
来源： https://developer.apple.com/documentation/SwiftUI/TabRole/search
抓取时间： 2025-12-03T05:59:44Z
---

# 搜索

**类型属性**

搜索角色。

## 声明

```swift
static var search: TabRole { get }
```

## 讨论

可搜索选项卡视图倾向于让具有此角色的第一个选项卡执行搜索。如果没有指定任何标签页作为搜索标签页，则标签页视图将对所有标签页应用搜索，并在所选标签页发生变化时重置搜索状态。


---
source: https://developer.apple.com/documentation/SwiftUI/TabRole/search
crawled: 2025-12-03T05:59:44Z
---

# search

**Type Property**

The search role.

## Declaration

```swift
static var search: TabRole { get }
```

## Discussion

Searchable tab views will prefer to have the first tab with this role implement search. If no tabs are specified as the search tab, the tab view will apply search to all tabs, resetting search state as the selected tab changes.

