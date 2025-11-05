# Open External Editor
Forked from [godot-addon-open-external-editor](https://github.com/krayon/godot-addon-open-external-editor).

Fixed some critical bugs.
## Summary

Godot's script editor is quite good, but if you're coming from Vim or Emacs,
moving around can feel sluggish.

It's already possible to write scripts in an external editor, but there's no way
to quickly switch back to the built-in editor (for, say, debugging) without
opening the editor settings and disabling the external editor.

This plugin gives you the best of both worlds by adding a button to the
top-right of the built-in script editor that opens the current script in your
defined external editor. When you save the script, Godot will detect the change
and automatically reload it.

![Screenshot](screenshot.png)

## Compatibility
- Godot 4 (`gd4`) version tested in:
  - v4.5

## Installation

```

## Usage

1. Install this in your project's `addons` directory;
2. Open your "Editor Settings" -> "Text Editor" -> "External" settings dialog;
3. Ensure "Use External Editor" is **unchecked** for this addon to work;
4. Configure your "Exec Path" and "Exec Flags"; then
5. Click the button or press the keybinding to launch the external editor.

## Configuration

### Keybinding/Shortcut

By default, the shortcut is set to `Ctrl+E` but this can be changed at the top
of the `open_external_editor.gd` script.

### Exec Flags

Within "Exec Flags", the following strings will be replaced:

  - `{file}`
    - The filename of the current file
  - `{line}`
    - The line the cursor is currently on
  - `{col}`
    - The column the cursor is currently on
```
#### Examples - gVim

```
Exec Path:  gvim
Exec Flags: "+call cursor({line}, {col})" {file}
```

#### Examples - Terminal Vim

```
Exec Path: [terminal]
Exec Flags: -e vim "+call cursor ({line}, {col})" {file}
```

#### Examples - Emacs

```
Exec Path: emacs
Exec Flags: +{line}:{col} {file}
```

#### Examples - Sublime Text (Windows)

```
Exec Path: C:\Program Files\Sublime Text 3\sublime_text
Exec Flags: {file}:{line}:{col}
```


## License

MIT - see [LICENSE](LICENSE) file.


