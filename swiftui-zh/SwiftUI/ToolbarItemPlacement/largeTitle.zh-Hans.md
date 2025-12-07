---
来源： https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement/largeTitle
抓取时间： 2025-12-03T06:03:16Z
---

# 大标题

**类型属性**

将项目置于导航栏的标题区域。

## 声明

```swift
static let largeTitle: ToolbarItemPlacement
```

## 讨论

该视图将在导航栏显示其标题越行时显示，并优先于提供给 `View.navigationTitle(_:)` 修改器的值。

```swift
struct ContentView: View {
    var body: some View {
        NavigationStack {
            DetailView()
                .navigationTitle("Title")
                .navigationSubtitle("Subtitle")
                .toolbar {
                    ToolbarItem(placement: .largeTitle) {
                        CustomLargeNavigationTitle()
                    }
                }
        }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement/largeTitle
crawled: 2025-12-03T06:03:16Z
---

# largeTitle

**Type Property**

Places the item in the title area of the navigation bar.

## Declaration

```swift
static let largeTitle: ToolbarItemPlacement
```

## Discussion

The view will be shown when the navigation bar renders its title out-of-line, and takes precedence over the value provided to the `View.navigationTitle(_:)` modifier.

```swift
struct ContentView: View {
    var body: some View {
        NavigationStack {
            DetailView()
                .navigationTitle("Title")
                .navigationSubtitle("Subtitle")
                .toolbar {
                    ToolbarItem(placement: .largeTitle) {
                        CustomLargeNavigationTitle()
                    }
                }
        }
    }
}
```

