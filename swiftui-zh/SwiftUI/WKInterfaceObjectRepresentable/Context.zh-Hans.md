--- 来源：https://developer.apple.com/documentation/SwiftUI/WKInterfaceObjectRepresentable/Context

抓取时间：2025-12-03T05:39:09Z

---

# WKInterfaceObjectRepresentable.Context | Apple 开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ WKInterfaceObjectRepresentable ](/documentation/swiftui/wkinterfaceobjectrepresentable)

- [ WKInterfaceObjectRepresentable.Context ](/documentation/SwiftUI/WKInterfaceObjectRepresentable/Context)

- [ WKInterfaceObjectRepresentable ](/documentation/swiftui/wkinterfaceobjectrepresentable)

- WKInterfaceObjectRepresentable.Context 

类型别名：WKInterfaceObjectRepresentable.Context

watchOS 6.0+

```
typealias Context = WKInterfaceObjectRepresentableContext<Self>
```

## [另请参阅](/documentation/SwiftUI/WKInterfaceObjectRepresentable/Context#see-also)

### [创建和更新接口] [/documentation/SwiftUI/WKInterfaceObjectRepresentable/Context#Creating-and-updating-the-interface-object]

[`func makeWKInterfaceObject(context: Self.Context) -> Self.WKInterfaceObjectType`](/documentation/swiftui/wkinterfaceobjectrepresentable/makewkinterfaceobject(context:))创建一个 WatchKit 接口对象并配置其初始状态。**Required**

[`func updateWKInterfaceObject(Self.WKInterfaceObjectType, context: Self.Context)`](/documentation/swiftui/wkinterfaceobjectrepresentable/updatewkinterfaceobject(_:context:))将呈现的 WatchKit 接口对象（及其协调器）更新为最新配置。**Required**

---
source: https://developer.apple.com/documentation/SwiftUI/WKInterfaceObjectRepresentable/Context
crawled: 2025-12-03T05:39:09Z
---

# WKInterfaceObjectRepresentable.Context | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ WKInterfaceObjectRepresentable ](/documentation/swiftui/wkinterfaceobjectrepresentable)

- [ WKInterfaceObjectRepresentable.Context ](/documentation/SwiftUI/WKInterfaceObjectRepresentable/Context)

- [ WKInterfaceObjectRepresentable ](/documentation/swiftui/wkinterfaceobjectrepresentable)

-  WKInterfaceObjectRepresentable.Context 

Type Alias# WKInterfaceObjectRepresentable.Context

watchOS 6.0+

```
typealias Context = WKInterfaceObjectRepresentableContext<Self>
```

## [See Also](/documentation/SwiftUI/WKInterfaceObjectRepresentable/Context#see-also)

### [Creating and updating the interface object](/documentation/SwiftUI/WKInterfaceObjectRepresentable/Context#Creating-and-updating-the-interface-object)

[`func makeWKInterfaceObject(context: Self.Context) -> Self.WKInterfaceObjectType`](/documentation/swiftui/wkinterfaceobjectrepresentable/makewkinterfaceobject(context:))Creates a WatchKit interface object and configures its initial state.**Required**

[`func updateWKInterfaceObject(Self.WKInterfaceObjectType, context: Self.Context)`](/documentation/swiftui/wkinterfaceobjectrepresentable/updatewkinterfaceobject(_:context:))Updates the presented WatchKit interface object (and its coordinator) to the latest configuration.**Required**