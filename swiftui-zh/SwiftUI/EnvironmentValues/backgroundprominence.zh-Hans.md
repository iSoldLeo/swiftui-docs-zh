---
来源： https://developer.apple.com/documentation/swiftui/environmentvalues/backgroundprominence
抓取时间： 2025-12-04T13:10:31Z
---

# 背景突出

**实例属性**

与此环境相关的视图下方背景的突出度。

## 声明

```swift
var backgroundProminence: BackgroundProminence { get set }
```

## 讨论

根据`colorScheme`，突出背景上方的前景元素通常会被调整为具有更高对比度的潜在鲜艳颜色，例如采用不透明度更高的单色外观。在这种情况下，`primary`、`secondary` 等系统样式会自动解析为适当的样式。该属性可被读取并用于自定义样式的元素。

在下面的示例中，一个自定义星级元素与一些文本一起位于列表行中。当选择该行并增加其突出显示时，文本和星级评价将更新其外观，星级评价将使用标准`secondary` 样式替换黄色。

```swift
struct RecipeList: View {
    var recipes: [Recipe]
    @Binding var selectedRecipe: Recipe.ID?

    var body: some View {
        List(recipes, selection: $selectedRecipe) {
            RecipeListRow(recipe: $0)
        }
    }
}

struct RecipeListRow: View {
    var recipe: Recipe
    var body: some View {
        VStack(alignment: .leading) {
            HStack(alignment: .firstTextBaseline) {
                Text(recipe.name)
                Spacer()
                StarRating(rating: recipe.rating)
            }
            Text(recipe.description)
                .foregroundStyle(.secondary)
                .lineLimit(2, reservesSpace: true)
        }
    }
}

private struct StarRating: View {
    var rating: Int

    @Environment(\.backgroundProminence)
    private var backgroundProminence

    var body: some View {
        HStack(spacing: 1) {
            ForEach(0..<rating, id: \.self) { _ in
                Image(systemName: "star.fill")
            }
        }
        .foregroundStyle(backgroundProminence == .increased ?
            AnyShapeStyle(.secondary) : AnyShapeStyle(.yellow))
        .imageScale(.small)
    }
}
```

请注意，使用`backgroundProminence` 的视图嵌套在行中的其他堆栈容器中。这确保了该值能正确反映列表行内的环境，而不是整个列表的环境。例如，确保正确解析的一种方法是在自定义 ShapeStyle 中使用该值：

```swift
private struct StarRating: View {
    var rating: Int

    var body: some View {
        HStack(spacing: 1) {
            ForEach(0..<rating, id: \.self) { _ in
                Image(systemName: "star.fill")
            }
        }
        .foregroundStyle(FillStyle())
        .imageScale(.small)
    }
}

extension StarRating {
    struct FillStyle: ShapeStyle {
        func resolve(in env: EnvironmentValues) -> some ShapeStyle {
            switch env.backgroundProminence {
            case .increased: return AnyShapeStyle(.secondary)
            default: return AnyShapeStyle(.yellow)
            }
        }
    }
}
```

`List` 和 `Table` 等视图以及 `ShapeStyle.selection` 等标准形状样式将自动更新前景视图的背景突出显示。对于自定义背景，可以在自定义背景上方的视图中明确设置此环境属性。

## 配置背景

- **listRowBackground(_:)**：在列表行项后面放置自定义背景视图。
- **alternatingRowBackgrounds(_:)**：覆盖此视图中的列表和表格是否具有交替行背景。
- **AlternatingRowBackgroundBehavior**：与交替行背景有关的视图样式。
- **BackgroundProminence**：其他视图下方背景的突出显示。


---
source: https://developer.apple.com/documentation/swiftui/environmentvalues/backgroundprominence
crawled: 2025-12-04T13:10:31Z
---

# backgroundProminence

**Instance Property**

The prominence of the background underneath views associated with this environment.

## Declaration

```swift
var backgroundProminence: BackgroundProminence { get set }
```

## Discussion

Foreground elements above an increased prominence background are typically adjusted to have higher contrast against a potentially vivid color, such as taking on a higher opacity monochrome appearance according to the `colorScheme`. System styles like `primary`, `secondary`, etc will automatically resolve to an appropriate style in this context. The property can be read and used for custom styled elements.

In the example below, a custom star rating element is in a list row alongside some text. When the row is selected and has an increased prominence appearance, the text and star rating will update their appearance, the star rating replacing its use of yellow with the standard `secondary` style.

```swift
struct RecipeList: View {
    var recipes: [Recipe]
    @Binding var selectedRecipe: Recipe.ID?

    var body: some View {
        List(recipes, selection: $selectedRecipe) {
            RecipeListRow(recipe: $0)
        }
    }
}

struct RecipeListRow: View {
    var recipe: Recipe
    var body: some View {
        VStack(alignment: .leading) {
            HStack(alignment: .firstTextBaseline) {
                Text(recipe.name)
                Spacer()
                StarRating(rating: recipe.rating)
            }
            Text(recipe.description)
                .foregroundStyle(.secondary)
                .lineLimit(2, reservesSpace: true)
        }
    }
}

private struct StarRating: View {
    var rating: Int

    @Environment(\.backgroundProminence)
    private var backgroundProminence

    var body: some View {
        HStack(spacing: 1) {
            ForEach(0..<rating, id: \.self) { _ in
                Image(systemName: "star.fill")
            }
        }
        .foregroundStyle(backgroundProminence == .increased ?
            AnyShapeStyle(.secondary) : AnyShapeStyle(.yellow))
        .imageScale(.small)
    }
}
```

Note that the use of `backgroundProminence` was used by a view that was nested in additional stack containers within the row. This ensured that the value correctly reflected the environment within the list row itself, as opposed to the environment of the list as a whole. One way to ensure correct resolution would be to prefer using this in a custom ShapeStyle instead, for example:

```swift
private struct StarRating: View {
    var rating: Int

    var body: some View {
        HStack(spacing: 1) {
            ForEach(0..<rating, id: \.self) { _ in
                Image(systemName: "star.fill")
            }
        }
        .foregroundStyle(FillStyle())
        .imageScale(.small)
    }
}

extension StarRating {
    struct FillStyle: ShapeStyle {
        func resolve(in env: EnvironmentValues) -> some ShapeStyle {
            switch env.backgroundProminence {
            case .increased: return AnyShapeStyle(.secondary)
            default: return AnyShapeStyle(.yellow)
            }
        }
    }
}
```

Views like `List` and `Table` as well as standard shape styles like `ShapeStyle.selection` will automatically update the background prominence of foreground views. For custom backgrounds, this environment property can be explicitly set on views above custom backgrounds.

## Configuring backgrounds

- **listRowBackground(_:)**: Places a custom background view behind a list row item.
- **alternatingRowBackgrounds(_:)**: Overrides whether lists and tables in this view have alternating row backgrounds.
- **AlternatingRowBackgroundBehavior**: The styling of views with respect to alternating row backgrounds.
- **BackgroundProminence**: The prominence of backgrounds underneath other views.

