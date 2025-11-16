---
description: Create a new Expo/React Native screen with TypeScript and modern best practices
model: claude-sonnet-4-5
---

Generate a new Expo/React Native screen following 2025 best practices.

## Screen Specification

$ARGUMENTS

## Modern Expo/React Native + TypeScript Standards

### 1. **Function Components Only**
- Use function components for screens.
- Utilize hooks for state and side effects (`useState`, `useEffect`, etc.).

### 2. **TypeScript Best Practices**
- Strict typing (`strict: true`).
- Type definitions for navigation props (e.g., using `@react-navigation/native`).
- No `any` types.

### 3. **Screen Structure**
- Organize screens in a dedicated `screens` or `features` directory.
- Use a clear and consistent naming convention (e.g., `HomeScreen.tsx`, `ProfileScreen.tsx`).

**Example Screen Structure**
```typescript
import React from 'react';
import { View, Text, StyleSheet } from 'react-native';
import { type NativeStackScreenProps } from '@react-navigation/native-stack';

// Define your RootStackParamList if you are using react-navigation
// type RootStackParamList = {
//   Home: undefined;
//   Details: { itemId: number };
// };

// type Props = NativeStackScreenProps<RootStackParamList, 'Home'>;

export function ScreenName() { // Add props here: { navigation, route }: Props
  return (
    <View style={styles.container}>
      <Text>Screen Content</Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
  },
});
```

### 4. **Navigation**
- Use a robust navigation library like **React Navigation**.
- Define a clear navigation structure (e.g., Stack, Tab, Drawer navigators).
- Type-check navigation props for safety.

### 5. **State Management**
- `useState` for local screen state.
- `useReducer` for more complex state logic.
- **Zustand** or **Redux Toolkit** for global state management across screens.
- **React Context** for theming or authentication data.

### 6. **Styling**
- Use **StyleSheet.create** for performance and organization.
- Consider using a universal styling library like **NativeWind** for cross-platform consistency.

### 7. **Data Fetching**
- Use a modern data fetching library like **React Query** or **RTK Query**.
- Handle loading, error, and empty states gracefully.
- Cache data to improve performance and user experience.

## What to Generate

1.  **Screen File**: The main screen component with TypeScript.
2.  **Navigation Types**: (If applicable) Type definitions for the screen's navigation props.
3.  **Styles**: Styles defined using `StyleSheet.create` or a universal styling library like NativeWind.
4.  **Example Usage**: How to integrate the screen into a navigator.

## Code Quality Standards

- **Structure**: Organize code within the screen for readability (e.g., state, effects, handlers, render).
- **TypeScript**: Use explicit types for all props, state, and function signatures.
- **Accessibility**: Implement accessibility props like `accessibilityLabel` and `accessibilityRole`.
- **Performance**: Optimize lists with `FlatList` or `SectionList`. Memoize expensive computations.

Generate a production-ready, accessible, and performant Expo/React Native screen.
