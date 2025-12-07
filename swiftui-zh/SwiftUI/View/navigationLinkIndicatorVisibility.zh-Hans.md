--- 来源：https://developer.apple.com/documentation/SwiftUI/View/navigationLinkIndicatorVisibility(_:)

抓取时间：2025-11-30T21:09:54Z

---

# navigationLinkIndicatorVisibility(_:)

**实例方法**

配置导航链接是否显示展开指示器。

## 声明

```swift
@MainActor @preconcurrency func navigationLinkIndicatorVisibility(_ visibility: Visibility) -> some View

```

## 说明

如果需要检测当前视图是否显示导航展开指示器，请参考 [navigationLinkIndicatorVisibility](../EnvironmentValues/navigationLinkIndicatorVisibility.zh-Hans.md) 环境变量的值。

以下示例隐藏列表中所有链接的展开指示器。可以通过在 `NavigationLink` 本身上添加修饰符来隐藏特定链接的展开指示器。

```swift
struct NoIndicatorLink: View {
    var body: some View {
        NavigationStack {
            List {
                NavigationLink("See detail") {
                    Text("Detail view")
                }
            }
            .navigationLinkIndicatorVisibility(.hidden)
        }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/navigationLinkIndicatorVisibility(_:)
crawled: 2025-11-30T21:09:54Z
---

# navigationLinkIndicatorVisibility(_:)

**Instance Method**

Configures whether navigation links show a disclosure indicator.

## Declaration

```swift
@MainActor @preconcurrency func navigationLinkIndicatorVisibility(_ visibility: Visibility) -> some View

```

## Discussion

If you need to detect whether the navigation disclosure indicator should be shown for the current view, read the [navigationLinkIndicatorVisibility](../EnvironmentValues/navigationLinkIndicatorVisibility.zh-Hans.md) environment value.

The following example hides the indicator for all links in the list. The indicator can be hidden for a specific link by placing the modifier on the `NavigationLink` itself.

```swift
struct NoIndicatorLink: View {
    var body: some View {
        NavigationStack {
            List {
                NavigationLink("See detail") {
                    Text("Detail view")
                }
            }
            .navigationLinkIndicatorVisibility(.hidden)
        }
    }
}
```



