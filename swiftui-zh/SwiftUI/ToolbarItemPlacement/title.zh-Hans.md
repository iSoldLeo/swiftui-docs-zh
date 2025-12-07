---
来源： https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement/title
抓取时间： 2025-12-03T06:03:17Z
---

# 标题

**类型属性**

将项目置于导航栏的标题区域。

## 声明

```swift
static var title: ToolbarItemPlacement { get }
```

## 讨论

该视图将在导航栏显示内嵌标题时显示，并优先于提供给`View.navigationTitle(_:)`修饰符的值。

```swift
struct ContentView: View {
    var body: some View {
        NavigationStack {
            DetailView()
                .navigationTitle("Title")
                .navigationSubtitle("Subtitle")
                .toolbar {
                    ToolbarItem(placement: .title) {
                        CustomNavigationTitle()
                    }
                }
        }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement/title
crawled: 2025-12-03T06:03:17Z
---

# title

**Type Property**

Places the item in the title area of the navigation bar.

## Declaration

```swift
static var title: ToolbarItemPlacement { get }
```

## Discussion

The view will be shown when the navigation bar renders its title inline, and takes precedence over the value provided to the `View.navigationTitle(_:)` modifier.

```swift
struct ContentView: View {
    var body: some View {
        NavigationStack {
            DetailView()
                .navigationTitle("Title")
                .navigationSubtitle("Subtitle")
                .toolbar {
                    ToolbarItem(placement: .title) {
                        CustomNavigationTitle()
                    }
                }
        }
    }
}
```

