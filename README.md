# Godot Dialog Manager

A Visual Studio Code extension that provides comprehensive syntax highlighting for Godot DialogueManager `.dialogue` files.

## Features

- **Complete syntax highlighting** for DialogueManager `.dialogue` files
- **Character dialogue lines** with optional character IDs
- **Player choices** with branching support
- **Conditional statements** (`if`, `elif`, `else`)
- **Variable mutations** (`do`, `set` commands)
- **Jump statements** for dialogue flow control
- **BBCode formatting** tags for rich text
- **Translation keys** support
- **Comment highlighting**
- **Section titles** for organizing dialogue
- **Proper indentation** and folding support

## Supported Syntax

### Character Dialogue
```dialogue
Nathan: Hello there!
Nathan[happy]: I'm feeling great today!
```

### Player Choices
```dialogue
- Hi Nathan! => greet_nathan
- *Leave quietly* => sneak_away
- [if has_item] Give him the item => give_item
```

### Conditional Logic
```dialogue
if player_level > 5:
    Nathan: You look experienced!
elif player_level > 2:
    Nathan: You're getting there.
else:
    Nathan: You're just starting out.
```

### Variable Operations
```dialogue
do player_score += 10
set player_name = "Hero"
set has_key = true
```

### Section Organization
```dialogue
~ start
Nathan: Welcome to the game!
=> town_square

~ town_square
Nathan: What would you like to do?
```

### BBCode Formatting
```dialogue
Nathan: This text is [b]bold[/b] and [color=red]red[/color]!
```

### Translation Support
```dialogue
Nathan: [TR:greeting_hello]
```

## Installation

1. Download the `.vsix` file
2. Open VS Code
3. Go to Extensions (`Ctrl+Shift+X`)
4. Click the `...` menu and select "Install from VSIX..."
5. Select the downloaded `.vsix` file

Alternatively, install from the command line:
```bash
code --install-extension godot-dialogue-manager-x.x.x.vsix
```

## Usage

1. Open any `.dialogue` file in VS Code
2. The extension will automatically provide syntax highlighting
3. Enjoy color-coded dialogue scripting!

## Example Dialogue File

```dialogue
# This is a comment
~ start

Nathan: Hey there, traveler!
Nathan[surprised]: I didn't expect to see you here.

- Hello Nathan! => friendly_greeting
- *Ignore him* => ignore_path
- [if player_has_weapon] *Threaten him* => threat_path

~ friendly_greeting

Nathan: It's great to see a friendly face!
do relationship_nathan += 1

if relationship_nathan > 5:
    Nathan: You're becoming a good friend.
    => close_friend
else:
    Nathan: Nice talking with you.
    => END

~ close_friend

Nathan: [b]You're my best friend![/b]
set nathan_best_friend = true
=> END

~ ignore_path

# Nathan gets sad
Nathan: [color=gray]Oh... okay then.[/color]
do relationship_nathan -= 1
=> END

~ threat_path

Nathan: [shake]Please don't hurt me![/shake]
set nathan_scared = true
=> END
```

## Language Features

- **Line comments** using `#`
- **Auto-closing pairs** for brackets and quotes
- **Smart indentation** for conditional blocks
- **Code folding** for dialogue sections
- **Bracket matching** for BBCode tags

## Requirements

- Visual Studio Code 1.74.0 or higher
- Godot DialogueManager plugin (for actual dialogue functionality)

## Known Issues

None currently reported. Please file issues on the GitHub repository.

## Contributing

Contributions are welcome! Please feel free to submit issues and pull requests.

## Release Notes

### 0.0.1

- Initial release
- Complete syntax highlighting for `.dialogue` files
- Support for all major DialogueManager features
- Language configuration for improved editing experience

## License

This extension is released under the MIT License.

---

**Enjoy writing dialogue for your Godot games!** 🎮✨