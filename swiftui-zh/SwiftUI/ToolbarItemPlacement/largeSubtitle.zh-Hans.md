---
来源： https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement/largeSubtitle
抓取时间： 2025-12-03T06:03:15Z
---

# largeSubtitle

**类型属性**

将项目置于导航栏的副标题区域。

## 声明

```swift
static let largeSubtitle: ToolbarItemPlacement
```

## 讨论

该视图会在导航栏显示其标题越行时显示，并优先于`View.navigationSubtitle(_:)`修饰符的值。

```swift
struct ContentView: View {
    var body: some View {
        NavigationStack {
            DetailView()
                .navigationTitle("Title")
                .navigationSubtitle("Subtitle")
                .toolbar {
                    ToolbarItem(placement: .largeSubtitle) {
                        CustomLargeNavigationSubtitle()
                    }
                }
        }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement/largeSubtitle
crawled: 2025-12-03T06:03:15Z
---

# largeSubtitle

**Type Property**

Places the item in the subtitle area of the navigation bar.

## Declaration

```swift
static let largeSubtitle: ToolbarItemPlacement
```

## Discussion

The view will be shown either when the navigation bar renders its title out-of-line, and takes precedence over the value provided to the `View.navigationSubtitle(_:)` modifier.

```swift
struct ContentView: View {
    var body: some View {
        NavigationStack {
            DetailView()
                .navigationTitle("Title")
                .navigationSubtitle("Subtitle")
                .toolbar {
                    ToolbarItem(placement: .largeSubtitle) {
                        CustomLargeNavigationSubtitle()
                    }
                }
        }
    }
}
```

