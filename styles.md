# Project Style Guide

## Overview
This project uses **clang-format** with a standardized C++ style configuration defined in `.clang-format`. All C++ code is formatted automatically using this configuration.

## Formatting Tool
- **Tool**: clang-format
- **Config**: `.clang-format`
- **Format Script**: `format.sh` (applies formatting to all source files in `src/`)

## Key Style Conventions

### Code Formatting
- **Indentation**: 4 spaces (C++ standard)
- **Brace Wrapping**: Configured per `.clang-format` rules
- **Alignment**:
  - Operands are aligned
  - Opening brackets aligned after parentheses
  - Trailing comments aligned
  - Access modifiers offset by -1 (one level to the left)

### Language & Structure
- **Language**: C++
- **Header Guards**: `#pragma once` (preferred over `#ifndef` guards)
- **Include Organization**:
  - System/library includes first (e.g., `<functional>`, `<iostream>`)
  - Project includes after (e.g., `"Keyhandle.hpp"`)
  - Grouped with blank lines between categories

### Naming Conventions
- **Classes**: PascalCase (e.g., `MutableObject`, `KeyHandle`)
- **Methods**: camelCase (e.g., `detectKeyPresses()`)
- **Variables**: camelCase (e.g., `ball`, `keyhandling`)
- **Constants**: Defined per context (check individual files)

### Function & Method Style
- **Short Functions**: Allowed on single line (per `AllowShortFunctionsOnASingleLine: All`)
- **Short Namespaces**: Must wrap (per `AllowShortNamespacesOnASingleLine: false`)
- **If Statements**: Short statements allowed without else (per `AllowShortIfStatementsOnASingleLine: WithoutElse`)
- **Loops**: Short loops may be on single line (per `AllowShortLoopsOnASingleLine: true`)

### Directory Structure
```
src/
├── Main.cpp                    # Main entry point
└── core/
    ├── Window.hpp/cpp          # Window management
    ├── Keyhandle.hpp/cpp       # Input handling
    └── object/
        ├── Collision.hpp/cpp   # Collision detection
        ├── MutableObject.hpp/cpp # Base object class
        └── Rotation.hpp        # Rotation utilities
```

## How to Format Code

Run the formatting script:
```bash
./format.sh
```

Or format individual files:
```bash
clang-format -i <file>.cpp
clang-format -i <file>.hpp
```

## Files Following This Style
- ✓ src/Main.cpp
- ✓ src/core/Window.hpp & .cpp
- ✓ src/core/Keyhandle.hpp & .cpp
- ✓ src/core/object/Collision.hpp & .cpp
- ✓ src/core/object/MutableObject.hpp & .cpp
- ✓ src/core/object/Rotation.hpp

## CI/CD Integration
The `.clang-format` configuration is checked during builds. Code must conform to this style to pass review.
