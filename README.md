# simpleMenuWizard

## Hide contextmenu items in Firefox 57+

This project is inspired by [this post](https://www.reddit.com/r/firefox/comments/7dvtw0/guide_how_to_edit_your_context_menu/) on [reddit.com/r/Firefox](https://www.reddit.com/r/firefox/) by [BubiBalboa](https://www.reddit.com/user/BubiBalboa)

## Instructions:

To **remove entries from the context menu** you need to 

1. Find your **profile folder**: Address bar > Enter `about:support` > Click `Open Folder`  

2. [Download](https://github.com/stonecrusher/simpleMenuWizard/archive/master.zip) and unzip this project

3. `userChrome.css` and `simpleMenuWizard` belong into *[...]\Profiles\\**profile.folder**\chrome\\* directory.

4. Now open the `simpleMenuWizard` directory and open each .css file with a texteditor to customize them to your needs.  
**Enabling** options: Remove /* at the beginning of the line  
**Disabling** options: Add /* at the beginning of the line

Mind that the **last active** option **must not have** a trailing comma.  
Items that appear in different contexts with same ID will disappear in all contexts when activated.
