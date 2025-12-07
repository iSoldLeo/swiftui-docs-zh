--- 来源：https://developer.apple.com/documentation/SwiftUI/View/controlSize(_:)

抓取时间：2025-11-30T21:21:19Z

---

# controlSize(_:)

**实例方法**

设置此视图中控件的大小。

## 声明

```swift
nonisolated func controlSize(_ controlSize: ControlSize) -> some View

```

## 参数

- **controlSize**：[ControlSize](../ControlSize.zh-Hans.md) 枚举中指定的控件大小之一。

## 说明

使用 `controlSize(_:)` 可以覆盖此视图中控件的系统默认大小。在本例中，视图以 `.mini`、`.small` 和 `.regular` 大小显示几个典型的控件。

```swift
struct ControlSize: View {
    var body: some View {
        VStack {
            MyControls(label: "Mini")
                .controlSize(.mini)
            MyControls(label: "Small")
                .controlSize(.small)
            MyControls(label: "Regular")
                .controlSize(.regular)
        }
        .padding()
        .frame(width: 450)
        .border(Color.gray)
    }
}

struct MyControls: View {
    var label: String
    @State private var value = 3.0
    @State private var selected = 1
    var body: some View {
        HStack {
            Text(label + ":")
            Picker("Selection", selection: $selected) {
                Text("option 1").tag(1)
                Text("option 2").tag(2)
                Text("option 3").tag(3)
            }
            Slider(value: $value, in: 1...10)
            Button("OK") { }
        }
    }
}
```

## 尺寸控制

- **controlSize**：应用于视图中控件的尺寸。

- **ControlSize**：可应用于视图中控件的尺寸类别，例如“常规”或“小”。


---
source: https://developer.apple.com/documentation/SwiftUI/View/controlSize(_:)
crawled: 2025-11-30T21:21:19Z
---

# controlSize(_:)

**Instance Method**

Sets the size for controls within this view.

## Declaration

```swift
nonisolated func controlSize(_ controlSize: ControlSize) -> some View

```

## Parameters

- **controlSize**: One of the control sizes specified in the [ControlSize](../ControlSize.zh-Hans.md) enumeration.

## Discussion

Use `controlSize(_:)` to override the system default size for controls in this view. In this example, a view displays several typical controls at `.mini`, `.small` and `.regular` sizes.

```swift
struct ControlSize: View {
    var body: some View {
        VStack {
            MyControls(label: "Mini")
                .controlSize(.mini)
            MyControls(label: "Small")
                .controlSize(.small)
            MyControls(label: "Regular")
                .controlSize(.regular)
        }
        .padding()
        .frame(width: 450)
        .border(Color.gray)
    }
}

struct MyControls: View {
    var label: String
    @State private var value = 3.0
    @State private var selected = 1
    var body: some View {
        HStack {
            Text(label + ":")
            Picker("Selection", selection: $selected) {
                Text("option 1").tag(1)
                Text("option 2").tag(2)
                Text("option 3").tag(3)
            }
            Slider(value: $value, in: 1...10)
            Button("OK") { }
        }
    }
}
```



## Sizing controls

- **controlSize**: The size to apply to controls within a view.
- **ControlSize**: The size classes, like regular or small, that you can apply to controls within a view.

