# simpleMenuWizard

Hide contextmenu items in Firefox 57+

This project is inspired by [this post](https://www.reddit.com/r/firefox/comments/7dvtw0/guide_how_to_edit_your_context_menu/) on [reddit.com/r/Firefox](https://www.reddit.com/r/firefox/) by [BubiBalboa](https://www.reddit.com/user/BubiBalboa)

## Instructions:

To **remove entries from the context menu** you need to 

1. Find your **profile folder**: Address bar > Enter `about:support` > Click `Open Folder`.

2. [Download this project](https://github.com/stonecrusher/simpleMenuWizard/archive/master.zip) and unzip it.

3. Move `userChrome.css` and `simpleMenuWizard` into *[...]\Profiles\\**profile.folder**\chrome\\* directory. If chrome folder doesn't exist, create it.

4. Now open the `simpleMenuWizard` directory and edit each .css file with a texteditor to customize them to your needs.  
**Activate** option: Remove `/*` at the beginning of the line  
**Deactivate** option: Add `/*` at the beginning of the line

Mind that the **last active** option **must not have** a trailing comma for [correct syntax](http://www.htmldog.com/guides/css/intermediate/grouping/).  

Edit [...]-context.css to modify context menu:

* `blank-context.css`	when right-clicking on a blank area on a webpage  
* `frame-context.css` when right-clicking on an iframe  
* `image-context.css` when right-clicking on an image  
* `input-context.css` when right-clicking on an input-field  
* `link-context.css` when right-clicking on a link  
* `media-context.css` when right-clicking on a playing media like audio or html5 video  
* `select-context.css` when right-clicking on selected text or selected object  
* `tab-context.css` when right-clicking on a tab  

Items that appear in different contexts with same ID will disappear in all contexts when activated.

## Contribute
For bugreports and missing items you're welcome to [open an issue here](https://github.com/stonecrusher/simpleMenuWizard/issues).

## Links
A great repository for modifications of the Firefox 57+ UI is [CustomCSSforFx](https://github.com/Aris-t2/CustomCSSforFx) by Aris
