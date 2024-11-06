
# Flutter App - Clean Architecture Using Bloc

This project follows the **Clean Architecture** principles to ensure maintainability, testability, and scalability. 
It is structured in a modular fashion with a separation of concerns, making it easy to add features and manage dependencies.

## Project Structure

```plaintext
lib
├── core                   # Core functionalities and shared components
│   ├── constants          # Application constants like images, URLs, etc.
│   ├── colors             # Color definitions for the entire app
│   ├── enum               # Enum types for managing states and other shared enums
│   ├── style              # App styles like text styles, padding, and themes
│   ├── usecase            # Defines use case implementations, outlining application business logic
│   ├── validation         # Input validation utilities for form validation, etc.
│   └── error              # Error handling classes, including custom exceptions and failure models
│
├── config                 # Application configuration, including themes and routes
│   ├── theme              # Global theme settings for the app
│   └── routes             # Route management files defining app navigation
│
├── features               # Feature-based modules, adhering to clean architecture principles
│   ├── auth               # Authentication-related functionality
│   │   ├── data           # Data sources, models, repositories
│   │   │   ├── datasources  # API services and data fetching sources
│   │   │   ├── repositories # Repository implementations bridging data sources and domain
│   │   │   └── entity       # Data models specific to data sources
│   │   ├── domain         # Domain models, repository interfaces, and use cases
│   │   │   ├── repositories # Abstract repository interfaces
│   │   │   ├── model        # Domain models, representing business entities
│   │   │   └── usecases     # Use cases representing specific business actions
│   │   └── presentation   # UI and Bloc (state management) for the feature
│   │       ├── screen       # Screens related to auth (e.g., login, signup)
│   │       ├── widgets      # Reusable widgets for auth (buttons, forms, etc.)
│   │       └── bloc         # BLoC files for state management (auth events, states, bloc)
│   ├── splash             # Splash screen feature setup with a similar structure
│   └── users              # User-related features (profile, user details, etc.), structured similarly
│
├── utils                  # Utility classes and helper functions (e.g., navigation, shared preferences)
│
└── widgets                # Shared widgets used across the app, such as custom buttons,appbar
```

## Folder Details

### `core`
Contains the shared and essential components like constants, themes, color schemes, and common use cases that are reused throughout the app.

### `config`
- **Routes**: Manages all app routes in a centralized manner.
- **Themes**: Defines the global themes for the app.

### `features`
Each feature (e.g., `auth`, `users`, `splash`) follows the Clean Architecture structure:
  - **data**: Manages data sources, such as remote or local data access, and repository implementations.
  - **domain**: Contains business logic, use cases, and domain entities.
  - **presentation**: Handles UI, widgets, and BLoC/Cubit files for state management.

### `utils`
Contains helper classes or functions that may be used across the app, like navigation helpers and shared preferences.

### `widgets`
Reusable widgets that are shared across various parts of the application.

## Getting Started

### Prerequisites

- [Flutter SDK](https://flutter.dev/docs/get-started/install)
- [Dart SDK](https://dart.dev/get-dart)

### Installation

Clone the repository and install dependencies.

```bash
git clone <My-Repository-Url>
cd ecom
flutter clean
flutter pub get
```

### Running the App

```bash
flutter run
```

## State Management

This project uses the BLoC (Business Logic Component) library for state management, ensuring a reactive and maintainable UI.

## Adding New Features

1. **Create a new folder** in `features` following the structure (data, domain, presentation).
2. **Define the data models, repositories, and use cases** in the respective folders.
3. **Implement BLoC or Cubit for state management** in the `presentation` layer.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any improvements.

---

### Note
This project structure is inspired by the Clean Architecture principles and provides a good foundation for scaling up your Flutter applications in a structured manner.
