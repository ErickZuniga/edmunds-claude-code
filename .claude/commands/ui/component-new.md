---
description: Create a new Expo/React Native component with TypeScript and modern best practices
model: claude-sonnet-4-5
---

Generate a new Expo/React Native component following 2025 best practices.

## Component Specification

$ARGUMENTS

## Modern Expo/React Native + TypeScript Standards

### 1. **Function Components Only**
- Use function components (not class components)
- React 19 patterns
- Platform-specific code (`.ios.tsx`, `.android.tsx`, `.web.tsx`)

### 2. **TypeScript Best Practices**
- Strict typing (`strict: true`)
- Interface for props
- Proper TypeScript utility types (ComponentProps, ReactNode, etc.)
- NO `any` types
- Explicit return types for complex components

### 3. **Component Patterns**

**Component Structure**
```typescript
import React from 'react';
import { View, Text, StyleSheet } from 'react-native';

interface Props {
  // typed props
}

export function Component({ }: Props) {
  return (
    <View style={styles.container}>
      <Text>Component</Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    // styles
  },
});
```

### 4. **State Management**
- `useState` for local state
- `useReducer` for complex state
- Zustand or Redux Toolkit for global state
- React Context for theme/auth

### 5. **Performance**
- Lazy loading with `React.lazy()`
- Code splitting
- `use memo()` for expensive computations
- `useCallback()` for callback functions

### 6. **Styling Approach** (choose based on project)
- **StyleSheet.create** - Default React Native styling
- **Styled Components** - CSS-in-JS for React Native
- **Tamagui / Nativewind** - Universal styling solutions

## What to Generate

1. **Component File** - Main component with TypeScript
2. **Props Interface** - Fully typed props
3. **Styles** - Using `StyleSheet.create`
4. **Example Usage** - How to import and use
5. **Storybook Story** (optional) - Component documentation

## Code Quality Standards

**Structure**
-   Feature-based folder organization
-   Co-locate related files
-   Barrel exports (index.ts)
-   Clear file naming conventions

**TypeScript**
-   Explicit prop types via interface
-   Proper generics where needed
-   Utility types (Pick, Omit, Partial)
-   Discriminated unions for variants

**Props**
-   Required vs optional props
-   Default values where appropriate
-   Destructure in function signature
-   Props spread carefully

**Accessibility**
-   `accessibilityLabel`, `accessibilityRole` props
-   Keyboard navigation
-   Screen reader friendly

**Best Practices**
-   Single Responsibility Principle
-   Composition over inheritance
-   Extract complex logic to hooks
-   Keep components small (<200 lines)

## Component Types to Consider

**Presentational Components**
- Pure UI rendering
- No business logic
- Receive data via props
- Easy to test

**Container Components**
- Data fetching
- Business logic
- State management
- Pass data to presentational components

**Compound Components**
- Related components working together
- Shared context
- Flexible API
- Example: `<Select><Select.Trigger/><Select.Content/></Select>`

## Expo/React Native Best Practices

- **Platform-Specific Logic**: Use `Platform.OS` or file extensions (`.ios.js`, `.android.js`, `.web.js`) for platform-specific code.
- **Performance**: Use `FlatList` or `SectionList` for long lists. Avoid anonymous functions in render methods.
- **Hooks**: Utilize hooks like `useWindowDimensions` for responsive layouts.
- **Expo APIs**: Leverage Expo's rich set of APIs for device features (camera, location, etc.).

Generate production-ready, accessible, and performant Expo/React Native components.
