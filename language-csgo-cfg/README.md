# CSGO cfg syntax highlighting

Adds syntax highlighting support for `.cfg` files

## Features

<blockquote>
  <p><code>autoexec.cfg</code> from my config <a href="https://pastebin.com/BDMe9dFK" target="_blank">config</a>
</blockquote>
<table>
  <tr>
    <td><img src="https://i.imgur.com/SSHPKrn.png" alt="Example without syntax highlighting" /></td>
    <td><img src="https://i.imgur.com/OCPCUSP.png" alt="Example with syntax highlighting" /></td>
  </tr>
  <tr>
    <td><i>Plain Text</i></td>
    <td><i>Using the <code><b>Dark+ (default dark)</b></code> theme</i></td>
  </tr>
</table>

This is the grammar I'm tagging:

- Comment
- Command
  - Unknown (deprecated, unused, or just unknown)
  - [Buttons/Keys](https://wiki.teamfortress.com/wiki/Scripting#List_of_key_names) (`SPACE`, `MOUSE1`)
  - Actions (`+attack`, `say_team`)
  - Settings (`alias`, `bind`, `r_drawviewmodel`)
- Numeric-Literal
- Variable (custom commands)
- Macros (`"+jump; +duck; +attack;"`)
- Punctuation-Semicolon

## Install

<ol>
  <li><a href="https://code.visualstudio.com/Download">Download</a> VS Code</li>
  <li>
    <p>Install the extension</p>
    <!–– <img src="https://i.imgur.com/IeOIXzc.png" alt="Install through VS Code" height="50%" width="50%" />
  </li>
</ol>

## Setup

<img src="https://i.imgur.com/ARqR6MK.png" height="75%" width="75%" />

1.  Open a `.cfg` file
1.  Click at the bottom right to change its "File Association" (Or press `Ctrl+K, Ctrl+M`)
1.  Select, `Configure File Association for '.cfg'...`
1.  Select `CSGO cfg` from the list

### Alternatively...

You can open your user settings (`Ctrl+,`) and add

```json
"files.associations": {
  "*.cfg": "CSGO cfg"
}
```

## Known Issues

- Not [all](https://developer.valvesoftware.com/wiki/List_of_CS:GO_Cvars) commands have been included yet
- Lazy regex checking, such as `r_\\w+` to mark anything that starts with `r_`, but really should only include exact commands
- My regex has not been reviewed and there's potentially a smarter way to be doing some of the things
- Ideally there'd be a custom color theme with property scope names (currently I'm using at least one `.js` name)

## Release Notes

### v0.0.1

- First Release
