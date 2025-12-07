--- 来源：https://developer.apple.com/documentation/SwiftUI/FileDialogBrowserOptions/enumeratePackages

抓取时间：2025-12-03T06:02:51Z

---

# enumeratePackages

**类型属性**

允许枚举包的内容，这与包以扁平方式表示（类似于文件）的默认行为不同。

## 声明

```swift
static let enumeratePackages: FileDialogBrowserOptions
```

## 获取浏览器选项

- **displayFileExtensions**：在 iOS 上，配置 `fileExporter`、`fileImporter` 或 `fileMover` 以显示或隐藏文件扩展名。默认行为是隐藏扩展名。在 macOS 上，此选项无效。

- **includeHiddenFiles**：显示默认隐藏的文件。


---
source: https://developer.apple.com/documentation/SwiftUI/FileDialogBrowserOptions/enumeratePackages
crawled: 2025-12-03T06:02:51Z
---

# enumeratePackages

**Type Property**

Allows enumerating packages contents in contrast to the default behavior when packages are represented flatly, similar to files.

## Declaration

```swift
static let enumeratePackages: FileDialogBrowserOptions
```

## Getting browser options

- **displayFileExtensions**: On iOS, configures the `fileExporter`, `fileImporter`, or `fileMover` to show or hide file extensions. Default behavior is to hide them. On macOS, this option has no effect.
- **includeHiddenFiles**: Displays the files that are hidden by default.

