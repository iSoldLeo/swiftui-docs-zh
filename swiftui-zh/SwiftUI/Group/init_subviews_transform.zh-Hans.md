---
来源：https://developer.apple.com/documentation/SwiftUI/Group/init(subviews:transform:)
抓取时间：2025-12-02T20:59:21Z
---

# init(subviews:transform:)

**Initializer**

用给定视图的子视图构建一个分组。

### 声明

```swift
init<Base, Result>(subviews view: Base, @ViewBuilder transform: @escaping (SubviewsCollection) -> Result) where Content == GroupElementsOfContent<Base, Result>, Base : View, Result : View
```

## 参数

- **view**：要获取子视图的视图。
- **transform**：从子视图集合构造视图的闭包。

### 讨论

使用该初始化器可以创建一个组，让您可以通过编程访问该组的子视图。下面的`CardsView` 根据你提供给它的视图集定义了组的结构：

```swift
struct CardsView<Content: View>: View {
    var content: Content

    init(@ViewBuilder content: () -> Content) {
        self.content = content()
    }

    var body: some View {
        VStack {
            Group(subviews: content) { subviews in
                HStack {
                    if subviews.count >= 2 {
                        SecondaryCard { subview[1] }
                    }
                    if let first = subviews.first {
                        FeatureCard { first }
                    }
                    if subviews.count >= 3 {
                        SecondaryCard { subviews[2] }
                    }
                }
                if subviews.count > 3 {
                    subviews[3...]
                }
            }
        }
    }
}
```

您可以使用`CardsView` 及其基于视图生成器的初始化程序来排列子视图集合：

```swift
CardsView {
    NavigationLink("What's New!") { WhatsNewView() }
    NavigationLink("Latest Hits") { LatestHitsView() }
    NavigationLink("Favorites") { FavoritesView() }
    NavigationLink("Playlists") { MyPlaylists() }
}
```

子视图集合按需构建子视图，因此只需访问集合中需要创建结果内容的部分即可。

子视图是它们所代表的视图的代理，这意味着应用于原始视图的修改器会先于应用于子视图的修改器生效。SwiftUI 会使用容器的环境而不是子视图代理的环境来解析视图。此外，由于子视图代表单个视图或容器，因此在应用样式后，子视图可能代表一个视图。因此，对子视图应用样式可能没有任何效果。


---
source: https://developer.apple.com/documentation/SwiftUI/Group/init(subviews:transform:)
crawled: 2025-12-02T20:59:21Z
---

# init(subviews:transform:)

**Initializer**

Constructs a group from the subviews of the given view.

## Declaration

```swift
init<Base, Result>(subviews view: Base, @ViewBuilder transform: @escaping (SubviewsCollection) -> Result) where Content == GroupElementsOfContent<Base, Result>, Base : View, Result : View
```

## Parameters

- **view**: The view to get the subviews of.
- **transform**: A closure that constructs a view from the collection of subviews.

## Discussion

Use this initializer to create a group that gives you programmatic access to the group’s subviews. The following `CardsView` defines the group’s structure based on the set of views that you provide to it:

```swift
struct CardsView<Content: View>: View {
    var content: Content

    init(@ViewBuilder content: () -> Content) {
        self.content = content()
    }

    var body: some View {
        VStack {
            Group(subviews: content) { subviews in
                HStack {
                    if subviews.count >= 2 {
                        SecondaryCard { subview[1] }
                    }
                    if let first = subviews.first {
                        FeatureCard { first }
                    }
                    if subviews.count >= 3 {
                        SecondaryCard { subviews[2] }
                    }
                }
                if subviews.count > 3 {
                    subviews[3...]
                }
            }
        }
    }
}
```

You can use `CardsView` with its view builder-based initializer to arrange a collection of subviews:

```swift
CardsView {
    NavigationLink("What's New!") { WhatsNewView() }
    NavigationLink("Latest Hits") { LatestHitsView() }
    NavigationLink("Favorites") { FavoritesView() }
    NavigationLink("Playlists") { MyPlaylists() }
}
```

Subviews collection constructs subviews on demand, so only access the part of the collection you need to create the resulting content.

Subviews are proxies to the view they represent, which means that modifiers that you apply to the original view take effect before modifiers that you apply to the subview. SwiftUI resolves the view using the environment of its container rather than the environment of its subview proxy. Additionally, because subviews represent a single view or container, a subview might represent a view after the application of styles. As a result, applying a style to a subview might have no effect.

