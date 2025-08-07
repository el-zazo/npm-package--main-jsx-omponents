# DarkBG Component

A simple, reusable dark background overlay component with Redux integration. DarkBG provides an elegant way to create modal-like experiences or highlight specific UI elements by dimming the rest of the page.

## Features

- 🖤 **Semi-Transparent Overlay** - Creates a dark, semi-transparent layer over your application
- 🔄 **Redux Integration** - Easy state management with Redux Toolkit
- 🎯 **Simple API** - Show and hide with simple Redux actions
- 📱 **Responsive** - Covers the entire viewport regardless of screen size
- 🔢 **Z-Index Control** - Properly layered to work with modals and popups

## Usage

```jsx
import { DarkBG } from "@el-zazo/main-jsx-omponents";

<DarkBG />;
```

## Redux Actions

### displayDarkBg

Shows the dark background overlay.

```jsx
import { displayDarkBg } from "@el-zazo/main-jsx-omponents";

dispatch(displayDarkBg());
```

### hideDarkBg

Hides the dark background overlay.

```jsx
import { hideDarkBg } from "@el-zazo/main-jsx-omponents";

dispatch(hideDarkBg());
```

## Example

```jsx
import { useDispatch } from "react-redux";
import { displayDarkBg, hideDarkBg } from "@el-zazo/main-jsx-omponents";

function YourComponent() {
  const dispatch = useDispatch();

  const showDarkBG = () => {
    dispatch(displayDarkBg());
  };

  const hideDarkBG = () => {
    dispatch(hideDarkBg());
  };

  // Auto-hide example
  const toggleDarkBG = () => {
    dispatch(displayDarkBg());
    setTimeout(() => dispatch(hideDarkBg()), 3000); // Auto-hide after 3 seconds
  };

  return (
    <div>
      <button onClick={showDarkBG}>Show Dark Background</button>
      <button onClick={hideDarkBG}>Hide Dark Background</button>
      <button onClick={toggleDarkBG}>Toggle Dark Background (Auto-hide)</button>
    </div>
  );
}
```
