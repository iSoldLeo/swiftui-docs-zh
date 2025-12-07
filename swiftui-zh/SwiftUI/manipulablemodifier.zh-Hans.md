--- 来源：https://developer.apple.com/documentation/swiftui/manipulablemodifier

抓取时间：2025-12-02T17:47:57Z

---

# ManipulableModifier | Apple 开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ ManipulableModifier ](/documentation/swiftui/manipulablemodifier)

- ManipulableModifier 

结构体# ManipulableModifier

visionOS 26.0+

```
nonisolated
struct ManipulableModifier
```

## [关联关系](/documentation/swiftui/manipulablemodifier#relationships)

### [符合](/documentation/swiftui/manipulablemodifier#conforms-to)

- [`ViewModifier`](/documentation/swiftui/viewmodifier)

## [另请参阅](/documentation/swiftui/manipulablemodifier#see-also)

### [修改视图](/documentation/swiftui/manipulablemodifier#Modifying-a-view)

[配置](/documentation/swiftui/manipulablemodifier#Modifying-a-view)视图](/documentation/swiftui/configuring-views)通过应用视图修饰符来调整视图的特性。[减少视图修饰符的维护](/documentation/swiftui/reducing-view-modifier-maintenance)将经常重用的视图修饰符捆绑到一个自定义视图修饰符中。[`func modifier<T>(T) -> ModifiedContent<Self, T>`](/documentation/swiftui/view/modifier(_:)将修饰符应用于视图并返回一个新视图。[`protocol ViewModifier`](/documentation/swiftui/viewmodifier)应用于视图或其他视图修饰符的修饰符，生成原始值的不同版本。[`struct EmptyModifier`](/documentation/swiftui/emptymodifier)空修饰符或标识修饰符，用于在开发期间在编译时切换修饰符。[`struct ModifiedContent`](/documentation/swiftui/modifiedcontent)具有应用于它的修饰符。[`protocol EnvironmentalModifier`](/documentation/swiftui/environmentalmodifier)必须在使用前解析为环境中的具体修饰符的修饰符。[`struct ManipulableResponderModifier`](/documentation/swiftui/manipulablerespondermodifier)[`struct ManipulableTransformBindingModifier`](/documentation/swiftui/manipulabletransformbindingmodifier)[`struct ManipulationGeometryModifier`](/documentation/swiftui/manipulationgeometrymodifier)[`struct ManipulationGestureModifier`](/documentation/swiftui/manipulationgesturemodifier)[`struct ManipulationUsingGestureStateModifier`](/documentation/swiftui/manipulationusinggesturestatemodifier)[`enum Manipulable`](/documentation/swiftui/manipulable)各种可操作相关类型的命名空间。

---
source: https://developer.apple.com/documentation/swiftui/manipulablemodifier
crawled: 2025-12-02T17:47:57Z
---

# ManipulableModifier | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ ManipulableModifier ](/documentation/swiftui/manipulablemodifier)

-  ManipulableModifier 

Structure# ManipulableModifier

visionOS 26.0+

```
nonisolated
struct ManipulableModifier
```

## [Relationships](/documentation/swiftui/manipulablemodifier#relationships)

### [Conforms To](/documentation/swiftui/manipulablemodifier#conforms-to)

- [`ViewModifier`](/documentation/swiftui/viewmodifier)

## [See Also](/documentation/swiftui/manipulablemodifier#see-also)

### [Modifying a view](/documentation/swiftui/manipulablemodifier#Modifying-a-view)

[Configuring views](/documentation/swiftui/configuring-views)Adjust the characteristics of a view by applying view modifiers.[Reducing view modifier maintenance](/documentation/swiftui/reducing-view-modifier-maintenance)Bundle view modifiers that you regularly reuse into a custom view modifier.[`func modifier<T>(T) -> ModifiedContent<Self, T>`](/documentation/swiftui/view/modifier(_:))Applies a modifier to a view and returns a new view.[`protocol ViewModifier`](/documentation/swiftui/viewmodifier)A modifier that you apply to a view or another view modifier, producing a different version of the original value.[`struct EmptyModifier`](/documentation/swiftui/emptymodifier)An empty, or identity, modifier, used during development to switch modifiers at compile time.[`struct ModifiedContent`](/documentation/swiftui/modifiedcontent)A value with a modifier applied to it.[`protocol EnvironmentalModifier`](/documentation/swiftui/environmentalmodifier)A modifier that must resolve to a concrete modifier in an environment before use.[`struct ManipulableResponderModifier`](/documentation/swiftui/manipulablerespondermodifier)[`struct ManipulableTransformBindingModifier`](/documentation/swiftui/manipulabletransformbindingmodifier)[`struct ManipulationGeometryModifier`](/documentation/swiftui/manipulationgeometrymodifier)[`struct ManipulationGestureModifier`](/documentation/swiftui/manipulationgesturemodifier)[`struct ManipulationUsingGestureStateModifier`](/documentation/swiftui/manipulationusinggesturestatemodifier)[`enum Manipulable`](/documentation/swiftui/manipulable)A namespace for various manipulable related types.