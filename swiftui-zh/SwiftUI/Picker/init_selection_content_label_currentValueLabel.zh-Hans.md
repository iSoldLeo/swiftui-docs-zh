---
来源：https://developer.apple.com/documentation/SwiftUI/Picker/init(selection:content:label:currentValueLabel:)
抓取时间：2025-12-02T21:55:16Z


# init(selection:content:label:currentValueLabel:)

**Initializer**

创建一个选取器，显示自定义标签和自定义值标签（如适用）。

### 声明

```swift
nonisolated init(selection: Binding<SelectionValue>, @ViewBuilder content: () -> Content, @ViewBuilder label: () -> Label, @ViewBuilder currentValueLabel: () -> some View)
```

## 参数

- **selection**：与属性的绑定，该属性决定当前选择的选项。
- **content**：包含选项集的视图。
- **label**：包含选项集的视图：描述选择某个选项的目的的视图。
- **currentValueLabel**：表示选取器当前值的视图。

## 讨论

下面的示例显示了一个带有当前值标签的选取器，该标签只显示当前所选歌曲的标题：

```swift
struct Song: Identifiable, Hashable {
    let id = UUID()
    let title: String
    let artist: String
    let genre: String
}

private let songs: [Song] = [ /* songs */]

@State private var selectedSong: Song? = nil

var body: some View {
    NavigationStack {
        List {
            Picker(selection: $selectedSong) {
                ForEach(songs) { song in
                    VStack(alignment: .leading) {
                        Text(song.title)
                            .bold()
                        Text(song.artist)
                        Text(song.genre)
                            .foregroundColor(.secondary)
                            .font(.caption)
                    }
                    .tag(song as Song?)
                }
            } label: {
                Text("Request a song")
            } currentValueLabel: {
                Text(selectedSong?.title ?? "No selection")
            }
        }
        .pickerStyle(.navigationLink)
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/Picker/init(selection:content:label:currentValueLabel:)
crawled: 2025-12-02T21:55:16Z
---

# init(selection:content:label:currentValueLabel:)

**Initializer**

Creates a picker that displays a custom label and a custom value label where applicable.

## Declaration

```swift
nonisolated init(selection: Binding<SelectionValue>, @ViewBuilder content: () -> Content, @ViewBuilder label: () -> Label, @ViewBuilder currentValueLabel: () -> some View)
```

## Parameters

- **selection**: A binding to a property that determines the currently-selected option.
- **content**: A view that contains the set of options.
- **label**: A view that describes the purpose of selecting an option.
- **currentValueLabel**: A view that represents the current value of the picker.

## Discussion

The following example shows a picker with a current value label that only displays the title of the currently selected song:

```swift
struct Song: Identifiable, Hashable {
    let id = UUID()
    let title: String
    let artist: String
    let genre: String
}

private let songs: [Song] = [ /* songs */]

@State private var selectedSong: Song? = nil

var body: some View {
    NavigationStack {
        List {
            Picker(selection: $selectedSong) {
                ForEach(songs) { song in
                    VStack(alignment: .leading) {
                        Text(song.title)
                            .bold()
                        Text(song.artist)
                        Text(song.genre)
                            .foregroundColor(.secondary)
                            .font(.caption)
                    }
                    .tag(song as Song?)
                }
            } label: {
                Text("Request a song")
            } currentValueLabel: {
                Text(selectedSong?.title ?? "No selection")
            }
        }
        .pickerStyle(.navigationLink)
    }
}
```

