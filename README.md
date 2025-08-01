# Layout Saver VS Code Extension

Layout Saver is a simple VS Code extension that lets you save and restore your editor layout—including tab groups, file positions, pinned tabs, and side bar visibility. Ideal for preserving your development workspace or quickly switching between tasks.

## Features

* Save the current editor layout (visible tabs, positions, and layout).
* Restore saved layouts with a single command.
* Optionally hide the side bar after restoring.
* Skips untitled or dirty tabs for safe restoring.

---

## Commands

| Command       | Title       | Description                      |
| ------------- | ----------- | -------------------------------- |
| `layout.save` | Save Layout | Saves the current editor layout. |
| `layout.load` | Load Layout | Loads the saved editor layout.   |

You can trigger these via the Command Palette (Ctrl+Shift+P) or bind custom keys.

Default keybinding:

* **Load Layout**: `Ctrl+Alt+L` (Windows/Linux), `Cmd+Alt+L` (macOS)

---

## Configuration Options

You can customize behavior through your settings (`settings.json`):

```json
{
  "layoutSaver.layout": {},
  "layoutSaver.hideSideBarAfterOpen": true
}
```

### Property Reference

* `layoutSaver.layout`: Internal storage for the saved layout.
* `layoutSaver.hideSideBarAfterOpen`: Hides the sidebar after layout is restored.

---

## Development

### Scripts

```bash
pnpm run esbuild        # One-time build using esbuild
pnpm run watch          # Watch for changes and rebuild
```

### Debugging

Launch the extension in a new Extension Host window using the included `launch.json` config.

---

## Known Limitations

* Webviews and terminal tabs cannot be restored (VS Code API limitation).
* Untitled tabs and dirty (unsaved) tabs are skipped when saving.

---

## License

GNU General Public License (GPL)

---

## Notice

This project builds upon [ctf0/vscode-save-editor-layout](https://github.com/ctf0/vscode-save-editor-layout) with custom modifications. Licensed under the GNU GPL.