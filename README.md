# Tmux Configuration and Plugin Installation Guide

This README provides detailed steps to back up your existing Tmux setup, set up your new Tmux configuration, and install the required plugins using the Tmux Plugin Manager (TPM).

## Prerequisites

- **Tmux**: Ensure you have Tmux installed on your system. You can check the version with:
  ```bash
  tmux -V
  ```
- **Git**: Required to clone the repository and install plugins.

## Backup Your Existing Tmux Setup

Before making any changes, it’s recommended to back up your current Tmux configuration and related files.

1. Check if you have an existing Tmux configuration file:
   ```bash
   ls ~/.tmux.conf ~/.config/tmux
   ```

2. Back up the existing configuration:
   ```bash
   mkdir -p ~/tmux-backup
   cp -r ~/.tmux.conf ~/.config/tmux ~/tmux-backup/
   ```

3. Verify the backup:
   ```bash
   ls ~/tmux-backup
   ```

   If you see your existing files in the `~/tmux-backup` directory, the backup was successful.

## Download the Configuration File

Clone the `tmux` configuration repository and save it under the `.config/` directory:

1. Clone the repository:
   ```bash
   git clone https://github.com/eugeniofciuvasile/tmux ~/.config/tmux
   ```

2. Verify the `tmux.conf` file:
   ```bash
   ls ~/.config/tmux/tmux.conf
   ```

   If you see the `tmux.conf` file, the clone was successful.

## Install Tmux Plugin Manager (TPM)

TPM is required to manage and install plugins listed in the `tmux.conf`. Follow the steps below:

1. Clone the TPM repository:
   ```bash
   git clone https://github.com/tmux-plugins/tpm ~/.config/tmux/.tmux/plugins/tpm
   ```

2. Verify the TPM installation:
   ```bash
   ls ~/.config/tmux/.tmux/plugins/tpm
   ```

   If you see files and directories related to TPM, the installation was successful.

## Install Plugins

After setting up the `tmux.conf` and installing TPM, follow these steps to install the plugins:

1. **Launch Tmux**:
   ```bash
   tmux
   ```

2. **Install Plugins**:
   Press `Prefix` (default is `Ctrl-b`) and then `I` (capital i) to install all the plugins listed in your `tmux.conf`.

3. **Verify Installation**:
   - Check if the plugins are installed in the directory:
     ```bash
     ~/.config/tmux/.tmux/plugins
     ```
   - Verify that the plugins are functional (e.g., try the commands or keybindings provided by the plugins).

## Plugins Used in This Configuration

The following plugins are included in the `tmux.conf`:

1. **[tmux-plugins/tpm](https://github.com/tmux-plugins/tpm)**:
   - Plugin manager for Tmux.
   
2. **[christoomey/vim-tmux-navigator](https://github.com/christoomey/vim-tmux-navigator)**:
   - Seamlessly navigate between Tmux panes and Vim splits.
   
3. **[omerxx/tmux-sessionx](https://github.com/omerxx/tmux-sessionx)**:
   - Manage Tmux sessions easily.
   
4. **[tmux-plugins/tmux-resurrect](https://github.com/tmux-plugins/tmux-resurrect)**:
   - Restore Tmux sessions after a system restart.
   
5. **[tmux-plugins/tmux-continuum](https://github.com/tmux-plugins/tmux-continuum)**:
   - Automatically save Tmux sessions every 15 minutes.
   
6. **[catppuccin/tmux](https://github.com/catppuccin/tmux)**:
   - Themed status bar and window appearance.
   
7. **[tmux-plugins/tmux-online-status](https://github.com/tmux-plugins/tmux-online-status)**:
   - Display online/offline status on the status bar.
   
8. **[tmux-plugins/tmux-battery](https://github.com/tmux-plugins/tmux-battery)**:
   - Display battery status on the status bar.

## Usage

- **Reload Configuration**: Reload the `tmux.conf` file without restarting Tmux:
  ```bash
  tmux source-file ~/.config/tmux/tmux.conf
  ```

- **Key Bindings**:
  - `Ctrl-b` + `r`: Reload configuration.
  - `Ctrl-b` + `%`: Horizontal split.
  - `Ctrl-b` + `"`: Vertical split.
  - `Ctrl-b` + `v`: Enter copy mode.
  - `Ctrl-b` + `f`: Open a new session using `tmux-sessionizer`.
  - `Ctrl-b` + `n`: Create a new session with a name prompt.
  - `Ctrl-b` + `m`: Maximize/restore current pane.

- **Mouse Support**:
  Tmux mouse mode is enabled, allowing you to click and drag to resize panes.

- **Session Persistence**:
  Use the `tmux-resurrect` and `tmux-continuum` plugins to save and restore sessions.

## Notes

- Ensure you have a terminal that supports True Color (e.g., `xterm-256color` or `alacritty`).
- Customize the `tmux.conf` file as needed to suit your preferences.

## Uninstalling Plugins

To uninstall a plugin:
1. Remove the plugin entry from `tmux.conf`.
2. Press `Prefix` (default is `Ctrl-b`) and `U` (capital u) to uninstall the plugin.

## Additional Information

For more details on each plugin, refer to their respective GitHub repositories linked above.

Enjoy your customized Tmux setup!
