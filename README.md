# Customize UI README

This experimental extension allows customizing VSCode user interface beyond what's normally possible, such as

- Changing interface fonts
- Inline titlebar on macOS
- Activity bar below sidebar
- Custom stylesheet rules conveniently specified in settings.json

<div style="text-align:center">
  <img src="https://raw.githubusercontent.com/iocave/customize-ui/master/screenshot.png" alt="Preview">
</div>

## Supported configuration options

### `customizeUI.activityBar`

When set to `bottom`, activity bar will be positioned below the sidebar.

### `customizeUI.titleBar`

macOS only. When set to `inline`, titlebar is hidden and window controls become part of sidebar.

### `customizeUI.fontSizeMap`

Mapping from hardcoded VSCode font size to custom font size. For example the following will change 13px and 12px UI fonts to 11px, which fixes huge sidebar font on OS X.

```jsonc
    "customizeUI.fontSizeMap": {
        "13px": "11px",
        "12px": "11px",
        "window-title": "12px", // Window title font when using custom titlebar
        "tab-title": "12px",    // Used for editor tab titles
        "monospace": "10.5px",  // Used for monospace fonts in user interface
        "menu": "13px",         // Used for menu items (windows only)
    }
```

### `customizeUI.listRowHeight`

Changes row height in various list and trees in user inteface. 22 by default

```jsonc
    "customizeUI.listRowHeight": 20, // shrink rows to match XCode
```

### `customizeUI.font.regular` and `customizeUI.font.monospace`

Allows changing font face for regular and monospace user interface fonts

```jsonc
    "customizeUI.font.regular": "Helvetica Nueve",
    "customizeUI.font.monospace": "Fira Code",
```

### `customizeUI.stylesheet`

Allow adding custom stylesheet rules. It is in form of a map where selectors are keys.

```jsonc
    "customizeUI.stylesheet": {
        ".search-view .search-widgets-container": "padding-top: 0px !important",
        ".suggest-input-container": "padding: 3px 4px 3px !important;"
    }
```

## How does it work

Customize UI relies on the [Monkey Patch Extension](https://marketplace.visualstudio.com/items?itemName=iocave.monkey-patch) to inject custom javascript in VSCode. After installation you should
be prompted to enable Monkey Patch. You can always trigger this manually by invoking the "Enable Monkey Patch" command.

## Credits

Inline titlebar inspired by Jürg Lehni's Titlebar-less VSCode extension.

