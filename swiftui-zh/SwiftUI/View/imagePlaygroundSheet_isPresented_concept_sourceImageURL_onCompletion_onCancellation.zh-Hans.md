--- 来源：https://developer.apple.com/documentation/SwiftUI/View/imagePlaygroundSheet(isPresented:concept:sourceImageURL:onCompletion:onCancellation:)

抓取时间：2025-12-02T17:24:02Z

---

# imagePlaygroundSheet(isPresented:concept:sourceImageURL:onCompletion:onCancellation:)

**实例方法**

显示系统工作表，以便根据指定的输入创建图像。

## 声明

```swift
@MainActor @preconcurrency func imagePlaygroundSheet(isPresented: Binding<Bool>, concept: String, sourceImageURL: URL, onCompletion: @escaping (URL) -> Void, onCancellation: (() -> Void)? = nil) -> some View

```

## 参数

- **isPresented**：绑定到一个布尔值，用于确定是否显示工作表。

- **concept**：描述图像预期内容的初始自然语言字符串。查看创建界面的用户可以在该界面内编辑概念。 `concept: str` 等同于 `concepts: [.text(str)]`。

- **sourceImageURL**：指向用于创建新图像的起始图像的文件 URL。查看此工作表的用户可以覆盖您提供的图像，并在创建界面中选择不同的图像和概念。如果您未提供起始图像，系统将创建新图像。

- **onCompletion**：用于接收已创建图像的代码块。此代码块没有返回值，并接收以下参数：

- **onCancellation**：当用户未选择图像而退出创建界面时要执行的代码块。执行此代码块后，系统将自动关闭工作表。

## 讨论

将此修饰符添加到视图以显示系统的图像创建工作表。当 `isPresented` 参数中的变量为 `true` 时，视图将显示工作表。在用户可能需要为其内容生成新图像的情况下，应显示此工作表。配置工作表时，可以指定一个可选的起始图像和文本描述，用于创建初始图像。

工作表可见时，用户可以在将图像返回到您的应用之前对其进行内容测试。查看工作表的用户可以选择接受他们创建的图像或取消操作。当用户做出选择时，系统将执行相应的代码块。

仅当设备支持创建新图像时，才能使用此修饰符。检查 `ImagePlayground/SwiftUICore/EnvironmentValues/supportsImagePlayground` 环境变量以确定此功能是否可用。以下代码创建一个按钮，仅当此功能可用时才显示工作表：

```swift
@State private var showSheet = false
@State private var createdImageURL: URL? = nil
@Environment(\.supportsImagePlayground) private var supportsImagePlayground
// ....

if supportsImagePlayground {
  Button("Show Generation Sheet") {
    showSheet = true
  }.imagePlaygroundSheet(
    isPresented: $showSheet,
    concept: "Dog on a surfboard",
    sourceImageURL: sourceImageURL) { url in
    createdImageURL = url
  }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/imagePlaygroundSheet(isPresented:concept:sourceImageURL:onCompletion:onCancellation:)
crawled: 2025-12-02T17:24:02Z
---

# imagePlaygroundSheet(isPresented:concept:sourceImageURL:onCompletion:onCancellation:)

**Instance Method**

Presents the system sheet to create images from the specified input.

## Declaration

```swift
@MainActor @preconcurrency func imagePlaygroundSheet(isPresented: Binding<Bool>, concept: String, sourceImageURL: URL, onCompletion: @escaping (URL) -> Void, onCancellation: (() -> Void)? = nil) -> some View

```

## Parameters

- **isPresented**: A binding to a Boolean value that determines whether to display the sheet.
- **concept**: An initial natural language string that describes the expected contents of the image. The person viewing the creation UI can edit the concepts from inside that UI. `concept: str` is equivalent to `concepts: [.text(str)]`.
- **sourceImageURL**: A file URL that refers to the image to use as the starting point for creating the new image. The person viewing the sheet can override the image you provide, and choose different images and concepts inside the creation UI. If you don’t provide a starting image, the system creates the new image.
- **onCompletion**: The block to receive the created image. The block has no return value and receives the following parameter:


- **onCancellation**: The block to execute when the person exits. the creation UI without choosing an image. After executing this block, the system automatically dismisses the sheet.

## Discussion

Add this modifier to a view to display the system’s image-creation sheet. When the variable in the `isPresented` parameter is `true`, the view presents the sheet. Present the sheet in situations where someone might want to generate a new image for their content. When configuring the sheet, specify an optional starting image and text description to use to create the initial image.

While visible, the sheet allows people to experiment with the contents of an image before returning it to your app. The person viewing the sheet can accept the image they created or cancel the operation. When they make their choice, the system executes the appropriate block.

You can use this modifier only if the device supports creating new images. Check the `ImagePlayground/SwiftUICore/EnvironmentValues/supportsImagePlayground` environment variable to determine the availability of the feature. The following code creates a button to display the sheet only when the feature is available:

```swift
@State private var showSheet = false
@State private var createdImageURL: URL? = nil
@Environment(\.supportsImagePlayground) private var supportsImagePlayground
// ....

if supportsImagePlayground {
  Button("Show Generation Sheet") {
    showSheet = true
  }.imagePlaygroundSheet(
    isPresented: $showSheet,
    concept: "Dog on a surfboard",
    sourceImageURL: sourceImageURL) { url in
    createdImageURL = url
  }
}
```

