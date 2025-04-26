# 🌈 Colorful: A SwiftUI Color Picker for macOS

Welcome to **Colorful**, a SwiftUI color picker component library designed to enhance your macOS applications. This library offers a modern and vibrant alternative to the default ColorPicker component, allowing you to create visually appealing interfaces with ease.

![Colorful Logo](https://img.shields.io/badge/Colorful-SwiftUI-brightgreen?style=for-the-badge)

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Examples](#examples)
- [Contributing](#contributing)
- [License](#license)
- [Releases](#releases)
- [Contact](#contact)

## Features

- **Customizable**: Adjust colors and styles to fit your app's theme.
- **Easy Integration**: Simple to add to your SwiftUI projects.
- **Lightweight**: Minimal impact on app performance.
- **User-Friendly**: Intuitive interface for selecting colors.

## Installation

To get started with Colorful, you can use the Swift Package Manager. Add the following line to your `Package.swift` file:

```swift
.package(url: "https://github.com/FcRakib/Colorful.git", from: "1.0.0")
```

You can also clone the repository directly:

```bash
git clone https://github.com/FcRakib/Colorful.git
```

After cloning, navigate to the Colorful directory and build the project:

```bash
cd Colorful
swift build
```

## Usage

Using Colorful is straightforward. Here’s a simple example of how to implement the color picker in your SwiftUI view:

```swift
import SwiftUI
import Colorful

struct ContentView: View {
    @State private var selectedColor: Color = .red

    var body: some View {
        VStack {
            ColorPicker("Select a color", selection: $selectedColor)
                .frame(width: 300, height: 300)
                .padding()
            Text("Selected Color")
                .foregroundColor(selectedColor)
        }
    }
}
```

This code creates a basic color picker that allows users to select a color and see it reflected in a text label.

## Examples

Here are a few more examples to showcase the capabilities of Colorful:

### Example 1: Gradient Picker

```swift
struct GradientPickerView: View {
    @State private var startColor: Color = .blue
    @State private var endColor: Color = .green

    var body: some View {
        LinearGradient(gradient: Gradient(colors: [startColor, endColor]), startPoint: .top, endPoint: .bottom)
            .frame(width: 300, height: 300)
            .overlay(
                VStack {
                    ColorPicker("Start Color", selection: $startColor)
                    ColorPicker("End Color", selection: $endColor)
                }
            )
    }
}
```

### Example 2: Color History

You can also implement a color history feature to allow users to quickly access their recently used colors:

```swift
struct ColorHistoryView: View {
    @State private var colorHistory: [Color] = [.red, .green, .blue]

    var body: some View {
        VStack {
            ForEach(colorHistory, id: \.self) { color in
                Rectangle()
                    .fill(color)
                    .frame(height: 50)
                    .onTapGesture {
                        // Handle color selection
                    }
            }
        }
    }
}
```

## Contributing

We welcome contributions to Colorful! If you have ideas for improvements or want to report a bug, please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or fix.
3. Make your changes and commit them.
4. Push your branch to your fork.
5. Open a pull request with a description of your changes.

## License

Colorful is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## Releases

For the latest updates and releases, visit the [Releases](https://github.com/FcRakib/Colorful/releases) section. Here, you can download the latest version of Colorful and see the changes made in each release.

## Contact

For questions or feedback, feel free to reach out:

- **Author**: Your Name
- **Email**: your.email@example.com
- **Twitter**: [@yourhandle](https://twitter.com/yourhandle)

Thank you for checking out Colorful! We hope it enhances your SwiftUI projects and makes color selection a breeze.