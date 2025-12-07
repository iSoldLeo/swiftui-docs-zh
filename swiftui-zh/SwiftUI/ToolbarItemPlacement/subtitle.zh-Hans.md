---
来源： https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement/subtitle
抓取时间： 2025-12-03T06:03:17Z
---

# 字幕

**类型属性**

将项目置于导航栏的副标题区域。

## 声明

```swift
static let subtitle: ToolbarItemPlacement
```

## 讨论

该视图将在导航栏显示内嵌标题时显示，并优先于提供给`View.navigationSubtitle(_:)`修饰符的值。

```swift
struct ContentView: View {
    var body: some View {
        NavigationStack {
            DetailView()
                .navigationTitle("Title")
                .navigationSubtitle("Subtitle")
                .toolbar {
                    ToolbarItem(placement: .subtitle) {
                        CustomNavigationSubtitle()
                    }
                }
        }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement/subtitle
crawled: 2025-12-03T06:03:17Z
---

# subtitle

**Type Property**

Places the item in the subtitle area of the navigation bar.

## Declaration

```swift
static let subtitle: ToolbarItemPlacement
```

## Discussion

The view will be shown when the navigation bar renders its title inline, and takes precedence over the value provided to the `View.navigationSubtitle(_:)` modifier.

```swift
struct ContentView: View {
    var body: some View {
        NavigationStack {
            DetailView()
                .navigationTitle("Title")
                .navigationSubtitle("Subtitle")
                .toolbar {
                    ToolbarItem(placement: .subtitle) {
                        CustomNavigationSubtitle()
                    }
                }
        }
    }
}
```

