---
layout: post
title:  "Hacked Atom a bit"
date:   2017-01-03 17:00:48
categories: atom coffeescript
---
## Added a timestamp menu item, localized to my taste

In `~/.atom/init.coffee`:

```
atom.commands.add 'atom-text-editor', 'Timestamp (swedish)', ->
  return unless editor = atom.workspace.getActiveTextEditor()

  selection = editor.getLastSelection()
  tstext = new Date().toLocaleString(["sv"])

  selection.insertText(tstext)
```

and in `~/.atom/keymap.cson`:

```
'atom-workspace':
  'ctrl-alt-shift-T': 'Timestamp (swedish)'
```

## Added a snippet for headers to jekyll posts

(And this is the first test!) In `~/.atom/snippets.cson`:

```
'.text.md':
  'jekyll.head':
    'prefix': 'jhd'
    'body': """
    ---
    layout: post
    title:  "$1"
    date:   $2
    categories: $3
    ---
    """
```
