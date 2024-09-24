# Aseprite Type Definitions 🖌️

## Introduction

The **Aseprite Type Definitions** provide comprehensive TypeScript typings for Aseprite's scripting API. These definitions allow you to use TypeScript's strong type-checking and IntelliSense capabilities while scripting for Aseprite. Additionally, these types are compatible with Lua, making it easy to integrate with Aseprite's scripting environment.

This project is designed for developers who wish to write Aseprite scripts in TypeScript and then compile them to Lua using **ts2lua**. The typings include everything from sprite manipulation to file handling, ensuring that your TypeScript code is aligned with Aseprite's API.

## Features ✨

- Full TypeScript type definitions for Aseprite API.
- Seamless integration with **ts2lua** for TypeScript-to-Lua compilation.
- Includes support for common Aseprite functionalities such as:
  - Animations
  - Blending modes
  - Color models
  - Tools and brushes
  - Dialog creation
  - Image manipulation

## Installation

You can install these type definitions using **npm**:

```bash
npm install types-aseprite
```

Alternatively, you can include these types manually in your TypeScript projects.

## Usage

Once installed, you can use these types directly in your TypeScript Aseprite scripts:

```typescript
import { AniDir, BlendMode, Image, Sprite, Color, Frame } from 'types-aseprite';

// Example: Create a new sprite and manipulate it
const sprite = new Sprite(32, 32);
const layer = sprite.newLayer();
const frame = sprite.newFrame();
sprite.resize(64, 64);

// Example: Using blend modes
const blendMode = BlendMode.OVERLAY;

// Example: Creating a color
const redColor = new Color({ r: 255, g: 0, b: 0 });
```

## Key Types Overview

### Animation Directions

```typescript
enum AniDir {
  FORWARD = 0,
  REVERSE,
  PING_PONG,
}
```

Defines animation directions for sprite tags in Aseprite.

### Blend Modes

```typescript
enum BlendMode {
  NORMAL = 0,
  MULTIPLY,
  SCREEN,
  OVERLAY,
  DARKEN,
  LIGHTEN,
  COLOR_DODGE,
  COLOR_BURN,
  HARD_LIGHT,
  SOFT_LIGHT,
  DIFFERENCE,
  EXCLUSION,
  HSL_HUE,
  HSL_SATURATION,
  HSL_COLOR,
  HSL_LUMINOSITY,
  ADDITION,
  SUBTRACT,
  DIVIDE,
}
```

The **BlendMode** enum defines various blending modes for layers and tools in Aseprite.

### Brushes

```typescript
enum BrushType {
  CIRCLE = 0,
  SQUARE,
  LINE,
  IMAGE,
}

enum BrushPattern {
  NONE = 0,
  ORIGIN,
  TARGET,
}
```

These enums define the different types and patterns of brushes you can use when drawing in Aseprite.

### Color and Pixel Manipulation

```typescript
declare class Color {
  constructor(colorConfig: ColorConfig);
  alpha: number;
  red: number;
  green: number;
  blue: number;
  // Other properties for HSL, HSV, and LAB values
}
```

Use the **Color** class to create and manipulate colors in Aseprite. Supports multiple color models like RGB, HSL, HSV, etc.

### Dialog and UI Components

```typescript
declare class Dialog {
  constructor(titleOrOptions?: string | DialogOptions);
  button(componentOptions: ComponentOptions): Dialog;
  show(componentOptions?: ComponentOptions): Dialog;
}
```

A **Dialog** class helps you create custom UI elements within Aseprite, such as buttons, sliders, and color pickers.

## Contributing

We welcome contributions to improve the type definitions or expand the supported Aseprite API surface. Please fork the repository, make your changes, and submit a pull request.

For detailed guidelines, refer to the [Contributing Guidelines](CONTRIBUTING.md).

## License

The Aseprite Type Definitions are released under the MIT License. Please refer to the [LICENSE](LICENSE) file for more details.

---

Created with ❤️ by JuanDAC and contributors.
