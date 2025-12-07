---
来源： https://developer.apple.com/documentation/SwiftUI/TabContent/draggable(_:)
抓取时间： 2025-12-01T10:50:48Z
---

# draggable(_:)

**实例方法**

将此标签页激活为拖放操作的源标签页。该选项卡只能在侧边栏中拖动。

## 声明

```swift
@MainActor @preconcurrency func draggable<T>(_ payload: @autoclosure @escaping () -> T) -> some TabContent<Self.TabValue> where T : Transferable

```

## 参数

- **payload**：返回单个实例或符合 [doc://com.apple.documentation/documentation/CoreTransferable/Transferable] 的值的闭包，该值表示此选项卡中的可拖动数据。

## 讨论

应用`draggable(_:)`修饰符可为该选项卡添加适当的拖放手势。拖动操作开始时，将生成该选项卡的渲染并用作预览图像。

下面的示例允许拖放 "家庭 "选项卡。

```swift
TabView {
    Tab("Family", systemImage: "list.bullet") {
        MyFamilyView()
    }
    .draggable(AppSections.family)
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/TabContent/draggable(_:)
crawled: 2025-12-01T10:50:48Z
---

# draggable(_:)

**Instance Method**

Activates this tab as the source of a drag and drop operation. This tab can only be dragged when in the sidebar.

## Declaration

```swift
@MainActor @preconcurrency func draggable<T>(_ payload: @autoclosure @escaping () -> T) -> some TabContent<Self.TabValue> where T : Transferable

```

## Parameters

- **payload**: A closure that returns a single instance or a value conforming to [doc://com.apple.documentation/documentation/CoreTransferable/Transferable] that represents the draggable data from this tab.

## Discussion

Applying the `draggable(_:)` modifier adds the appropriate gestures for drag and drop to this tab. When a drag operation begins, a rendering of the tab is generated and used as the preview image.

The following example allows the ‘Family’ tab to be dragged and dropped.

```swift
TabView {
    Tab("Family", systemImage: "list.bullet") {
        MyFamilyView()
    }
    .draggable(AppSections.family)
}
```

