---
来源：https://developer.apple.com/documentation/SwiftUI/Color/init(_:bundle:)
抓取时间： 2025-12-01T10:28:37Z
---

# init(_:bundle:)

**Initializer**

从您指定的颜色集中创建颜色。

### 声明

```swift
init(_ name: String, bundle: Bundle? = nil)
```

## 参数

- **name**：要查找的颜色资源名称。
- **bundle**：要查找颜色资源的捆绑包。如果未指定捆绑包，初始化程序将默认在应用程序的主捆绑包中查找。

## 讨论

使用此初始化程序可从存储在资产目录中的颜色集中加载颜色。系统会根据渲染时的环境来决定使用颜色集中的哪一种颜色。例如，您可以为背景色和前景色提供浅色和深色版本：



然后，您可以通过引用资产名称来实例化颜色：

```swift
struct Hello: View {
    var body: some View {
        ZStack {
            Color("background")
            Text("Hello, world!")
                .foregroundStyle(Color("foreground"))
        }
        .frame(width: 200, height: 100)
    }
}
```

SwiftUI 会为每个外观渲染相应的颜色：



## 创建颜色

- **init(_:)**：创建一个常量颜色，其数值由解析的颜色指定。
- **resolve(in:)**：根据当前`context`，将此颜色评估为已解析颜色。


---
source: https://developer.apple.com/documentation/SwiftUI/Color/init(_:bundle:)
crawled: 2025-12-01T10:28:37Z
---

# init(_:bundle:)

**Initializer**

Creates a color from a color set that you indicate by name.

## Declaration

```swift
init(_ name: String, bundle: Bundle? = nil)
```

## Parameters

- **name**: The name of the color resource to look up.
- **bundle**: The bundle in which to search for the color resource. If you don’t indicate a bundle, the initializer looks in your app’s main bundle by default.

## Discussion

Use this initializer to load a color from a color set stored in an Asset Catalog. The system determines which color within the set to use based on the environment at render time. For example, you can provide light and dark versions for background and foreground colors:



You can then instantiate colors by referencing the names of the assets:

```swift
struct Hello: View {
    var body: some View {
        ZStack {
            Color("background")
            Text("Hello, world!")
                .foregroundStyle(Color("foreground"))
        }
        .frame(width: 200, height: 100)
    }
}
```

SwiftUI renders the appropriate colors for each appearance:



## Creating a color

- **init(_:)**: Creates a constant color with the values specified by the resolved color.
- **resolve(in:)**: Evaluates this color to a resolved color given the current `context`.

