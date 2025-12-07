---
来源： https://developer.apple.com/documentation/SwiftUI/NavigationView/init(内容：)
抓取时间： 2025-12-03T05:43:12Z
---

# init(content:)

**Initializer**

创建基于目的地的导航视图。

## 声明

```swift
init(@ViewBuilder content: () -> Content)
```

## 参数

- **content**：用于生成导航视图封装内容的[ViewBuilder](../ViewBuilder.zh-Hans.md)。第一个视图之后的任何视图都是多栏显示中相应列的占位符。

##讨论

通过使用目标视图初始化链接来执行导航。例如，考虑一个显示颜色样本的`ColorDetail`视图：

```swift
struct ColorDetail: View {
    var color: Color

    var body: some View {
        color
            .frame(width: 200, height: 200)
            .navigationTitle(color.description.capitalized)
    }
}
```

下面的[NavigationView](../NavigationView.zh-Hans.md) 显示了三个指向颜色详细视图的链接：

```swift
NavigationView {
    List {
        NavigationLink("Purple", destination: ColorDetail(color: .purple))
        NavigationLink("Pink", destination: ColorDetail(color: .pink))
        NavigationLink("Orange", destination: ColorDetail(color: .orange))
    }
    .navigationTitle("Colors")

    Text("Select a Color") // A placeholder to show before selection.
}
```

当横向尺寸类别为[regular](../UserInterfaceSizeClass/regular.zh-Hans.md)时，例如在横向模式的 iPad 或 Mac 上，导航视图会以多栏视图的形式显示，并使用其第二个和后面的内容视图--上例中的单个[Text](../Text.zh-Hans.md)视图--作为相应栏的占位符：



当用户从列表中选择其中一个导航链接时，链接的目标视图会替换详细栏中的占位符文本：



当尺寸类别为[compact](../UserInterfaceSizeClass/compact.zh-Hans.md)时，比如在纵向方向的 iPhone 上，导航视图会显示为单列，用户可以堆叠方式浏览。点击其中一个链接，列表就会显示为详细视图，并提供一个返回按钮来返回列表：




---
source: https://developer.apple.com/documentation/SwiftUI/NavigationView/init(content:)
crawled: 2025-12-03T05:43:12Z
---

# init(content:)

**Initializer**

Creates a destination-based navigation view.

## Declaration

```swift
init(@ViewBuilder content: () -> Content)
```

## Parameters

- **content**: A [ViewBuilder](../ViewBuilder.zh-Hans.md) that produces the content that the navigation view wraps. Any views after the first act as placeholders for corresponding columns in a multicolumn display.

## Discussion

Perform navigation by initializing a link with a destination view. For example, consider a `ColorDetail` view that displays a color sample:

```swift
struct ColorDetail: View {
    var color: Color

    var body: some View {
        color
            .frame(width: 200, height: 200)
            .navigationTitle(color.description.capitalized)
    }
}
```

The following [NavigationView](../NavigationView.zh-Hans.md) presents three links to color detail views:

```swift
NavigationView {
    List {
        NavigationLink("Purple", destination: ColorDetail(color: .purple))
        NavigationLink("Pink", destination: ColorDetail(color: .pink))
        NavigationLink("Orange", destination: ColorDetail(color: .orange))
    }
    .navigationTitle("Colors")

    Text("Select a Color") // A placeholder to show before selection.
}
```

When the horizontal size class is [regular](../UserInterfaceSizeClass/regular.zh-Hans.md), like on an iPad in landscape mode, or on a Mac, the navigation view presents itself as a multicolumn view, using its second and later content views — a single [Text](../Text.zh-Hans.md) view in the example above — as a placeholder for the corresponding column:



When the user selects one of the navigation links from the list, the linked destination view replaces the placeholder text in the detail column:



When the size class is [compact](../UserInterfaceSizeClass/compact.zh-Hans.md), like on an iPhone in portrait orientation, the navigation view presents itself as a single column that the user navigates as a stack. Tapping one of the links replaces the list with the detail view, which provides a back button to return to the list:



