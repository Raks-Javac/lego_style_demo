# LEGO Style Demo Monorepo

A modular Flutter monorepo demonstrating scalable app architecture using [Melos](https://melos.invertase.dev/) for multi-package management.

## Project Structure

```
lego_style_demo/
├── app/
│   ├── lego_app/           # Main Flutter application
│   ├── lego_configuration/ # Configuration package
│   ├── lego_navigation/    # Navigation package
├── core/
│   └── design_system/      # Shared design system
├── feature/
│   ├── harry_potter/       # Harry Potter feature module
│   └── lego_list/          # Lego List feature module
├── analysis_options.yaml
├── README.md
└── pubspec.yaml            # Workspace root
```

## Monorepo Management with Melos
This project uses [Melos](https://melos.invertase.dev/) to manage multiple Dart/Flutter packages in a single repository.

### Setup & Installation
1. **Install Melos globally:**
   ```sh
dart pub global activate melos
   ```
2. **Install Melos in the workspace:**
   At the root, add Melos as a dev dependency:
   ```sh
dart pub add melos --dev
   ```
3. **Bootstrap the workspace:**
   ```sh
melos bootstrap
   ```
   This installs all package dependencies and links local packages.

### Package Configuration
- Each package (e.g., `lego_app`, `lego_configuration`, etc.) has its own `pubspec.yaml`.
- Add `resolution: workspace` to each package's `pubspec.yaml` for proper dependency resolution.

## Packages & Features
- **app/lego_app**: Main Flutter app entry point.
- **app/lego_configuration**: Handles app configuration and DI setup.
- **app/lego_navigation**: Manages navigation logic and routing.
- **core/design_system**: Shared UI theme and components.
- **feature/harry_potter**: Example feature module.
- **feature/lego_list**: Lego list feature with tests and localization.

## Usage
- Run the main app:
  ```sh
cd app/lego_app
fvm flutter run
  ```
- Run tests for a package:
  ```sh
melos exec -- "flutter test"
  ```
- Format code across all packages:
  ```sh
melos format
  ```

## Contributing
1. Fork the repo and create your branch.
2. Add new features as separate packages/modules.
3. Ensure all packages are bootstrapped and tested with Melos.
4. Submit a pull request.