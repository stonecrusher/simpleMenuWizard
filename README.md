# simpleMenuWizard

Hide contextmenu items in Firefox 57+

---

This project is inspired by [this post](https://www.reddit.com/r/firefox/comments/7dvtw0/guide_how_to_edit_your_context_menu/) on [reddit.com/r/Firefox](https://www.reddit.com/r/firefox/) and by [this issue](https://github.com/Aris-t2/CustomCSSforFx/issues/76) in the great [CustomCSSforFx](https://github.com/Aris-t2/CustomCSSforFx) project.

I made it because I am missing [Menu Wizard addon](https://addons.mozilla.org/de/firefox/addon/s3menu-wizard/) in Firefox 57 like many others.

## Instructions:

To **remove entries from the context menu** you need to 

1. Find your **profile folder**: Address bar > Enter `about:support` > Click `Open Folder`.

2. [Download this project](https://github.com/stonecrusher/simpleMenuWizard/archive/master.zip) and unzip it.

3. Move `userChrome.css` and `simpleMenuWizard` into *[...]\Profiles\\**profile.folder**\chrome\\* directory. If chrome folder doesn't exist, create it.

4. Now open the `simpleMenuWizard` directory and edit each .css file with a texteditor to customize them to your needs.  
**Activate** option to remove menu item: Remove `/*` at the beginning of the line  
**Deactivate** option to leave menu item: Add `/*` at the beginning of the line

Edit [...]-context.css to modify context menu:

* `blank-context.css`	when right-clicking on a blank area or text
* `frame-context.css` when right-clicking on an iframe  
* `image-context.css` when right-clicking on an image  
* `input-context.css` when right-clicking on an input-field  
* `link-context.css` when right-clicking on a link  
* `media-context.css` when right-clicking on media like audio or html5 video  
* `select-context.css` when right-clicking on selected text or object  
* `tab-context.css` when right-clicking on a tab  

Items that appear in different contexts with same ID will disappear in all contexts when activated.

## To do
Context menus not included yet:
* Right click anywhere in adress bar
* Right click in sidebar (bookmarks + history)
* Left click on (main) hamburger menu

## Contribute
For bugreports and missing items you're welcome to [open an issue here](https://github.com/stonecrusher/simpleMenuWizard/issues) or make a pull request.
