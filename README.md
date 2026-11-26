# ClassIIE

> A Qt desktop application for managing classroom reservations at ENSIIE.

## Overview

ClassIIE is a course project for the 2026 LAOA project at ENSIIE. It aims to help organize classroom use by bringing room, reservation, equipment, and participant information together in one application.

The project is currently at an early stage: the repository contains the Qt Widgets application scaffold. The capabilities below describe the intended scope and should not be read as features already implemented.

## Features

Planned capabilities:

- Create, view, edit, and remove classroom reservations.
- Allocate rooms to modules and student cohorts (promotions).
- Record room capacity, type, and available equipment...
- Assign instructors and students to the relevant rooms and reservations.
- Manage backup rooms for unexpected events.
- Support recurring weekly reservations and identify scheduling conflicts.
- Search and filter the managed information.
- Import and export application data.

## Tech Stack

- C++17
- Qt Widgets (Qt 5 or Qt 6)
- CMake 3.16 or newer

## Architecture

The application is intended to follow Qt's model/view approach, separating the reservation and room data model from its presentation and editing controls. The data model is expected to represent related entities such as rooms, reservations, modules, cohorts, equipment, and participants.

The codebase is still an early Qt Widgets scaffold centered on `MainWindow`. It contains empty model class declarations matching the domain entities in the class diagram; their attributes, relationships, and reservation workflows are not implemented yet. The `view` and `controller` folders are currently placeholders.

## Requirements

To build the project, install:

- A C++17-compatible compiler.
- CMake 3.16 or newer.
- Qt Widgets development files for either Qt 5 or Qt 6.

## Installation

Clone the repository, then configure and build it with CMake:

```sh
git clone https://github.com/OthmaneCHAOUI/classeroom-reservation-manager.git
cd classeroom-reservation-manager
cmake -S . -B build
cmake --build build
```

If CMake cannot locate Qt, install the Qt Widgets development package for your platform or set `CMAKE_PREFIX_PATH` to your Qt installation when configuring:

```sh
cmake -S . -B build -DCMAKE_PREFIX_PATH=/path/to/Qt
```

## Configuration

There are no application-specific configuration files or environment variables at this stage. Qt and compiler discovery are handled by CMake.

## Usage

After building, launch the executable:

```sh
./build/classeroom-reservation-manager
```

On Windows, run `build\classeroom-reservation-manager.exe` instead. The current scaffold opens the main application window; reservation management workflows are planned.

## Testing

No automated test suite is configured yet. Build the project to verify that the application compiles in your environment:

```sh
cmake --build build
```

## Project Structure

```text
.
├── docs/                 # LAOA project brief and project proposal
├── CMakeLists.txt        # Build configuration
├── main.cpp             # Application entry point
├── mainwindow.h/.cpp    # Main window scaffold
├── mainwindow.ui        # Qt Designer UI
├── src/
│   ├── controller/       # Controller placeholders
│   ├── model/            # Domain model class declarations
│   └── view/              # View placeholders
└── README.md
```

## Potential Improvements

- Define and document the domain model and its class diagram.
- Implement reservation and room management with conflict validation.
- Add Qt models and views for browsing, searching, and editing records.
- Implement data import/export and provide sample data.
- Add automated tests, screenshots, and user documentation.

## Contributing

Contributions are welcome. Before opening a pull request, please:

1. Keep changes focused and follow the existing C++ and Qt patterns.
2. Build the application with the CMake commands above.
3. Describe the change and any relevant testing in your pull request.

## License

This project is distributed under the [MIT License](./LICENSE).
