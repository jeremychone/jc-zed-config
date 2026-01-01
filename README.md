# Jeremy Chone Zed Config

Just to share, ccherry-pick what you need. 

Related Repos: 
- [jc-zed-config (this one)](https://github.com/jeremychone/jc-zed-config)
- [jc-zed-tasks](https://github.com/jeremychone/jc-zed-tasks)

## Keymap

- `cmd-shift-enter` Add line above and stay at end of line.
- `ctrl-cmd-enter` Add line below and stay at end of line.
- `cmd-backspace` Delete current line.
- `cmd-[` Move current line down.
- `cmd-]` Move current line up.
- `ctrl-alt-]` Indent line.
- `ctrl-alt-[` Outdent line.
- `cmd-;` End line with `;`.
- `ctrl-alt-r` Send 'r' keystroke to terminal.
- `ctrl-cmd-j` Spawn Dev Term (Below).
- `ctrl-cmd-shift-j` Spawn Dev Term (Bottom).
- `cmd-r` Run AIP task.
- `ctrl-cmd-a` Toggle AI.
- `ctrl-alt-,` Surround selection with `< >`.
- `ctrl-alt-9` Surround selection with `( )`.
- `cmd-shift-g` Toggle Git panel focus.
- `ctrl-cmd-right` Split pane and move right.
- `cmd-u` Toggle inlay hints.
- `alt-cmd-r` Toggle right dock.
- `alt-g` Select next match.
- `alt-shift-g` Select previous match.
- `alt-cmd-o` Open file/project.
- `cmd-o` Open recent projects.
- `ctrl-cmd-z` Toggle pane zoom.

### Sequence and Surround Techniques

The configuration utilizes `action::Sequence` to chain multiple editor commands into a single shortcut, such as moving the cursor after creating a newline.

For the surround functionality, the config uses `workspace::SendKeystrokes` to simulate a sequence of "command-x" (cut), typing the opening character, "command-v" (paste), and typing the closing character. This provides a simple way to wrap text without complex plugins.

## Tasks

The tasks defined in `tasks.json` rely on a custom utility called [jc-zed-tasks](https://github.com/jeremychone/rust-jc-zed-tasks). This is a centralized Rust-based CLI (available in a separate repository) designed to manage terminal positions, tmux integration, and AI toggling within the Zed environment.

- Terminal Management (via [jc-zed-tasks](https://github.com/jeremychone/rust-jc-zed-tasks))
  - `Dev Term Below` Opens a development terminal in a pane below with tmux.
  - `Dev Term Bottom` Opens a development terminal in a pane at the bottom with tmux.
- AI & AIP (via [jc-zed-tasks](https://github.com/jeremychone/rust-jc-zed-tasks))
  - `Toggle AI` Toggles Zed AI functionality via .
    - Otherwise, even when "subtle" we see some UI elements follow cursor. 
  - `AIP RUN` Send the 'r' to the first `aip` (AIPack) tmux pane. 
  - `pro@coder` Runs AIP task specifically in the `pro@coder` tmux pane. (since AIPack set the agent name as pane title in tmux)
- External Tools
  - `Fork here` Opens Fork git client at the project root.
  - `WezTerm` Opens WezTerm terminal emulator at the project root.
- Debug & Others
  - `DEBUG: print ZED vars` Displays environment variables containing "ZED".
  - `Example task` A demonstration task showing shell execution and configuration options.

## Settings

The `settings.json` file is organized into several functional sections:

- UI Bars: Configures the project panel, tab bar, and toolbar visibility to maintain a clean interface.
- AI and Completion: Sets up Copilot as the prediction provider and configures the `copilot_chat` agent with specific models.
- Editor: Defines standard indentation (tabs vs spaces), tab sizes, and inlay hint behavior.
- Languages: Provides specific overrides for Rust, Lua, Markdown, and YAML, ensuring appropriate formatting and prediction settings per language.
- LSP: Customizes `rust-analyzer` and JSON language server behaviors.
- Theme Overrides: Heavily modifies the "VSCode Dark Modern" theme to use pure black backgrounds and custom syntax coloring for a high-contrast experience.
- Terminal and Fonts: Configures font families (MesloLGS Nerd Font, Source Code Pro) and sizes for both the editor and the terminal.


## Info

License: Apache OR MIT


[This Repo](https://github.com/jeremychone/jc-zed-config)
