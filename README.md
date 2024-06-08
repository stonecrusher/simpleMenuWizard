# simpleMenuWizard
Hide default context menu items in Firefox release versions

---

## Instructions

To **remove entries from the context menu** you need to

1. Find your **profile folder** (profile names are different for everyone):  
   Address bar > Enter `about:support` > Click `Open Folder` (second one, not the "Update Folder").

2. [Download this project](https://github.com/stonecrusher/simpleMenuWizard/archive/master.zip) and unzip it.

3. Move `userChrome.css` and `simpleMenuWizard` into `[...]\profile folder\chrome\` directory.  
   If `chrome` folder doesn't exist, create it.  
   If `userChrome.css` already exists, do *not* overwrite and proceed [here](https://github.com/stonecrusher/simpleMenuWizard#using-simplemenuwizard-together-with-other-custom-modifications).

4. Open `userChrome.css` with a texteditor for a general overview and some options.

5. Open the `simpleMenuWizard` directory and edit each .css file to customize them to your needs.  
  **Remove menu item**: Remove `/*` at the beginning of the line.  
  **Leave menu item**: Add `/*` to the beginning of the line (by default every option is deactivated).

    Each file is for another context:

    * `blank-context.css`	when right-clicking on a blank area or text
    * `frame-context.css` when right-clicking on an iframe
    * `image-context.css` when right-clicking on an image
    * `input-context.css` when right-clicking on an input-field
    * `link-context.css` when right-clicking on a link
    * `main-hamburger.css` when **left**-clicking on the three lines on top right
    * `main-menubar.css` when **left**-clicking on the main menubar (open with ALT key - file, edit, view, ...)
    * `media-context.css` when right-clicking on media like audio or html5 video
    * `newtab-containers.css` when right-clicking on the plus sign to open a new tab or container
    * `select-context.css` when right-clicking on selected text or object
    * `sidebar-context.css` when right-clicking on items in bookmark- or history sidebar
    * `sidebar-header.css` when **left**-clicking the sidebar dropdown menu
    * `source-context.css` when right-clicking a blank area on view-source pages
    * `tab-context.css` when right-clicking on a tab
    * `toolbar-context.css` when right-clicking on toolbar or tabbar
    * `urlbar-context.css` when right-clicking on the addressbar

6. Load `about:config` into addressbar. Search for `toolkit.legacyUserProfileCustomizations.stylesheets` and make sure the value is `true`.

7. Restart Firefox to make changes work.

**Important notes:**
 * All *options and items are disabled by default*, so if you don't edit the files, nothing will happen.
 * If you're running macOS, make sure you set `widget.macos.native-context-menus` to `false` otherwise it won't work.
 * Items that appear in different contexts with the same ID will disappear in all those contexts when *activated only once*. This is because many menus internally share the same very big context menu and are separated here for convenience.  
   For specific problems please [open an issue](https://github.com/stonecrusher/simpleMenuWizard/issues), there may be workarounds.

## Hide Pocket / Sync / Screenshots
If you don't use either of those "internal addons" at all, you can just disable them, which will also remove their context menu entries everywhere.

How to do it: Load `about:config` into addressbar and set the respective value.

- Pocket: Search for `extensions.pocket.enabled` and switch to `false`.
- Sync: Search for `identity.fxaccounts.enabled` and switch to `false`.
- Screenshots: Search for `extensions.screenshots.disabled` and switch to `true`.

## Using simpleMenuWizard together with other custom modifications

Easiest thing to do is renaming the `userChrome.css` that came with the zip package of simpleMenuWizard.
Rename it to `simpleMenuWizard.css` and put it into `chrome` directory next to the already existing `userChrome.css`.

Open the old `userChrome.css` which is filled with foreign code and add `@import url("./simpleMenuWizard.css");` to the very top. That's it!

You can now edit `simpleMenuWizard.css` for a general overview and some options or continue with [step 5](https://github.com/stonecrusher/simpleMenuWizard#instructions).

## Uninstall simpleMenuWizard

Delete all the files and folders that came with this project.  
So if you don't use other modifications, you can simply delete the whole `[...]\profile folder\chrome\` directory.  
Restart your browser.

## Contribute
For bugreports and missing items you're welcome to [open an issue here](https://github.com/stonecrusher/simpleMenuWizard/issues) or make a pull request.

## Motivation
Tidy up your context menus, be faster, have a cleaner UI!

This project is inspired by [BubiBalboa's post on reddit](https://www.reddit.com/r/firefox/comments/7dvtw0/guide_how_to_edit_your_context_menu/) and by [an issue](https://github.com/Aris-t2/CustomCSSforFx/issues/76) in the great [CustomCSSforFx](https://github.com/Aris-t2/CustomCSSforFx/issues/2) project.
