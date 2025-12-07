--- 来源：https://developer.apple.com/documentation/SwiftUI/View/alternatingRowBackgrounds(_:)

抓取时间：2025-12-02T17:39:38Z

---

# alternatingRowBackgrounds(_:)

**实例方法**

重写此视图中的列表和表格是否具有交替行背景。

## 声明

```swift
nonisolated func alternatingRowBackgrounds(_ behavior: AlternatingRowBackgroundBehavior = .enabled) -> some View

```

## 参数

- **behavior**：是否启用交替行背景。

## 说明

此方法可以与显式列表或表格样式结合使用，也可以单独使用，以自定义自动样式的行背景。唯一不受此设置影响的列表样式是 `.sidebar.`

```swift
List(recipe.ingredients) {
    Text($0.name)
}
.listStyle(.bordered)
.alternatingRowBackgrounds()
```

此设置可与 `scrollContentBackground(_:)` 结合使用，在列表或表格的整体背景之上应用交替行背景。

此设置也可与 `listRowBackground` 结合使用，后者会覆盖特定列表行的背景，替换该行的自动交替背景。

## 配置背景

- **listRowBackground(_:)**：在列表行项后放置自定义背景视图。

- **AlternatingRowBackgroundBehavior**：设置视图相对于交替行背景的样式。

- **backgroundProminence**：设置与此环境关联的视图下方背景的突出显示程度。

- **BackgroundProminence**：背景在其他视图下方的突出程度。


---
source: https://developer.apple.com/documentation/SwiftUI/View/alternatingRowBackgrounds(_:)
crawled: 2025-12-02T17:39:38Z
---

# alternatingRowBackgrounds(_:)

**Instance Method**

Overrides whether lists and tables in this view have alternating row backgrounds.

## Declaration

```swift
nonisolated func alternatingRowBackgrounds(_ behavior: AlternatingRowBackgroundBehavior = .enabled) -> some View

```

## Parameters

- **behavior**: Whether alternating row backgrounds are enabled or not.

## Discussion

This can be used in conjunction with an explicit list or table style or used by itself to customize the row backgrounds of the automatic style. The only list style this has no effect on is `.sidebar.`

```swift
List(recipe.ingredients) {
    Text($0.name)
}
.listStyle(.bordered)
.alternatingRowBackgrounds()
```

This is able to be combined with `scrollContentBackground(_:)` and applies an alternating row background on top of the overall list or table background.

This can also be combined with `listRowBackground`, which overrides the background for a specific list row, replacing the automatic alternating background for that row.

## Configuring backgrounds

- **listRowBackground(_:)**: Places a custom background view behind a list row item.
- **AlternatingRowBackgroundBehavior**: The styling of views with respect to alternating row backgrounds.
- **backgroundProminence**: The prominence of the background underneath views associated with this environment.
- **BackgroundProminence**: The prominence of backgrounds underneath other views.

