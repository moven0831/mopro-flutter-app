# Mopro Flutter Example App

## Prerequisites

Before you begin, ensure you have the following installed:

*   **Flutter SDK:** Version >= 3.10. Follow the [official Flutter installation guide](https://docs.flutter.dev/get-started/install).
*   **Rust:** Required for building the native mopro components. Follow the [official Rust installation guide](https://www.rust-lang.org/tools/install).
*   **Xcode & Command Line Tools:** (For iOS development) Install from the Mac App Store. Ensure command-line tools are set up (`xcode-select --install`).
*   **Android Studio & NDK:** (For Android development) Install from the [official website](https://developer.android.com/studio). Ensure the Android SDK and NDK are configured (usually handled by Android Studio setup).
*   **CMake:** Required for native builds. Install via package managers (e.g., `brew install cmake` on macOS, `sudo apt-get install cmake` on Debian/Ubuntu).
*   **cbindgen:** For generating C bindings from Rust code. Install with `cargo install --force cbindgen`.

## Getting Started

1.  **Clone the Repository:**
    ```bash
    git clone https://github.com/zkmopro/mopro-flutter-app.git
    cd mopro-flutter-app
    ```

2.  **Navigate to the Flutter Project:**
    The example app is located within the `flutter/` directory.
    ```bash
    cd flutter
    ```
    *Note: The rest of the commands should be run from this `flutter/` directory.*

3.  **Install Flutter Dependencies:**
    This command also triggers the build process for the native Rust libraries used by the app via the `mopro_flutter_package`.
    ```bash
    flutter pub get
    ```

4.  **Prepare Your Device/Emulator:**
    *   Ensure you have an iOS Simulator or Android Emulator running.
    *   Alternatively, connect a physical device.
    *   Verify the device is recognized by Flutter:
        ```bash
        flutter devices
        ```

5.  **Run the App:**
    ```bash
    flutter run
    ```

## Project Structure

```
mopro-flutter-app/
├── flutter/          # Flutter application code
│   ├── lib/
│   ├── ios/
│   ├── android/
│   ├── pubspec.yaml
│   └── ...
├── src/              # Root Rust library source code
├── test-vectors/     # Test data for circuits
├── build.rs          # Rust build script
├── Cargo.toml        # Rust project manifest
├── README.md         # This file
└── ...
```

## Development Notes

*   If you modify the Rust code in the root directory (`src/`, `Cargo.toml`, etc.), you may need to run `flutter clean` and then `flutter pub get` again in the `flutter/` directory to trigger a rebuild of the native libraries.
*   Consult the main [mopro repository](https://github.com/zkmopro/mopro) for more details on the underlying Rust libraries and circuit development.

## Troubleshooting

*   **Build Errors during `flutter pub get`:**
    *   Ensure all prerequisites (Rust, cbindgen, CMake, NDK/Xcode) are installed correctly and available in your system's PATH.
    *   Check the specific error messages in the console output for clues.
    *   Try running `flutter clean` in the `flutter/` directory and then `flutter pub get` again.
*   **App runtime issues:** Verify the native libraries were built correctly and are included in the final app bundle.

## Contributing

Contributions are welcome! Please refer to the main [mopro repository](https://github.com/zkmopro/mopro) for contribution guidelines.

## License

This project is licensed under the MIT License and Apache License 2.0. See the `LICENSE-MIT` and `LICENSE-APACHE` files in the `flutter/` directory or the [LICENSE](https://github.com/zkmopro/mopro/blob/main/LICENSE) file in the main mopro repository for details.