Sublime Text 3
==============

Install Package Control extension
---------------------------------

https://sublime.wbond.net/installation

Install plugins
---------------

1.  Open the **command pallete** (`Ctrl+Shift+P`)
2.  Type `install` and select `Package Control: Install Package`

### Plugins

*   sublimelinter
*   sublimelinter jshint
*   soda theme
*   emmet
*   docblockr
*   tern for sublime: follow instructions at https://github.com/marijnh/tern_for_sublime

Configuration
-------------

Edit user preferences (`Preferences > Settings - User`)

### Disable automatic loading of last session

```json
{
  "hot_exit": false,
  "remember_open_files": false
}
```

### Disable word wrap

```json
{
  "word_wrap": "false"
}
```

### Indentation

```json
{
  "tab_size": 2,
  "translate_tabs_to_spaces": true
}
```

### Tern

```json
{
  "auto_complete_triggers": [{
    "selector": "source.js",
    "characters": "."
	}]
}
```
