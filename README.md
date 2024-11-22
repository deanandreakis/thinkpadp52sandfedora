# How I installed and configured a ThinkPad P52s with Fedora Workstation 40

I purchased a Lenovo ThinkPad P52s and installed Fedora Workstatopn 40 on it. I want to document the steps I had to go thru for this in case I need to do it again in the future.

1. Using Fedora MediaWriter I created a bootable USB stick with Fedora Workstation 40 on it.

2. I connected the USB stick to the P52s and booted into the Fedora installation program.

3. During the installation make sure to choose to overwrite the entire disk.

4. Once installation is complete, reboot and login and run 'dnf' command from the cli to make sure you have the latest updates.

5. Install the correct NVIDIA graphics drivers. This repo has a utility that will guide you thru the process: https://github.com/gridhead/nvidia-auto-installer-for-fedora-linux.

6. Install other apps and utilities as required: Chrome, Alacritty, Espanso, zsh, oh-my-zsh, neoVim, etc.

7. Install the MesloLS NF font from here: https://github.com/romkatv/powerlevel10k?tab=readme-ov-file#meslo-nerd-font-patched-for-powerlevel10k

8. Install GNOME Tweaks and enable sub pixel rendering and disable the CAPS lock key on the keyuboard.

9. For Alacritty make sure that the themes directory is cloned. See https://github.com/alacritty/alacritty-theme.

10. Installed the stripe-cli by just downloading and unzipping the executable and installed the firebase-cli via npm.

11. Created a GNOME shell extensions account. Use Firefox to access gnome extensions as chrome flatpak wont work.

12. Enabled usb-c charging mode on monitor so it keeps laptop charged without the need for a separate ac adapter.

13. Installed the uv python tool from https://github.com/astral-sh/uv?tab=readme-ov-file using there shell script.

14. I installed Homebrew.

15. For tmux package manager I had to clone the repo into .tmux again. See https://github.com/tmux-plugins/tpm.

Current Annoyances:
1. I have to open the laptop lid to resume from suspend state. If I leave the monitor on then I can just resume from keypresses.
2. The Espanso text expander service needs to be restarted after resume in order to work.
3. Window positions across suspend/resume are not saved.
4. Apps are not re-opened on a reboot.
5. After update to Fedora Workstation 41 none of the built-in apps would launch. I had to edit the /etc/environment file and add GSK_RENDERER=gl.
6. In KDE after resume from sleep the panel sometimes disappears. Use the following command to restart the plasma shell:
kquitapp6 plasmashell || kstart plasmashell
