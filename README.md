# Pamac-Fix

## Introduction
This repo introduces several Quality-of-Life improvements to Pamac and libpamac which are, in my opinion, long overdue. This is still in the development stage, and the releases for now are marked pre-release. 

## Major improvements in Pamac-Fix
- Improved and coordinated AUR and development-package updates — Avoids repeatedly checking the same -git and other development-package sources when recent results can safely be reused.
- More responsive graphical interface — Users can continue browsing and searching for packages while lengthy AUR and development-package update checks run in the background.
- Improved update progress reporting — More informative progress indicators in both the GUI and CLI, including individual development packages being checked.
- Better AUR dependency resolution — Improved handling of SONAME dependencies and split packages, including an optional Build and Verify workflow for dependencies that cannot be resolved until an AUR package is built.
- Coordinated update checking — The GUI, CLI, and system tray share update-check results where possible, eliminating unnecessary duplicate checks and improving notification responsiveness.
- Added safeguards to prevent two separate Pamac processes from overwriting the same build directory mid-build in the middle of a build, which can cause significant build issues.
- Improved system tray support — Native Wayland compatibility alongside X11 support, with more immediate and reliable update notifications.
- Expanded Flatpak management — Flatpak upgrade support in the CLI and an optional setting to automatically clean up unused Flatpak runtimes after application removal.
- Interactive Update check button on the interface.

## Installation
- The pkgbuild is a joined pkgbuild which replaces libpamac, pamac, and pamac-cli. There is no longer a need to install three separate packages. Simply download the pkgbuild, put it into a directory, and build the package normally.
- Note: please review your /etc/pamac.conf.pacsave files post-installation to retain any custom settings you have currently.

## Source Repositories
This repo is the forward-facing repo which joins the three components of pamac together. It takes from three repos:
- [libpamac-fix](https://github.com/username227/libpamac-fix)
- [pamac-cli-fix](https://github.com/username227/pamac-cli-fix)
- [pamac-gtk-fix](https://github.com/username227/pamac-gtk-fix)
To review the code that is underlying this pkgbuild, please visit these three repos.

## Development Warning
This package should be considered an experimental release at this point. It has undergone real-world testing but still requires additional testing to ensure its stability. Any issues or troubles that arise should be reported under Issues.
