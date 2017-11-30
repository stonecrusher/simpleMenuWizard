# simpleMenuWizard
Hide contextmenu items in Firefox 57+


https://www.reddit.com/r/firefox/comments/7dvtw0/guide_how_to_edit_your_context_menu/

**Step by step guide on how to edit the context menu of Firefox 57+**

First, **get the CSS selectors** of the elements you want to edit.

Here is a chart and list of most (?) CSS selectors of the context menu:

[right click menu](https://imgur.com/b5gEfUy) 

[right click on selected link](https://imgur.com/e9AaMx3) 

[List for copy/paste](https://pastebin.com/R3A5nJjv)

If an element is missing from the list or you want to know how to get the selectors by hand:
  
1. [Enable Browser Toolbox](https://developer.mozilla.org/en-US/docs/Tools/Browser_Toolbox#Enabling_the_Browser_Toolbox) if you haven't done so already.
2. For [debugging popups](https://developer.mozilla.org/en-US/docs/Tools/Browser_Toolbox#Debugging_popups), click the icon that [looks like 4 squares](https://mdn.mozillademos.org/files/12742/browser-toolbox-autohide-button.png) on the top right. This will make the context  menu stay visible. 
3. Switch to the browser window, right click somewhere to make the context menu show up.
4. Switch back to the Browser Toolbox, click the icon on the top left that looks like a pointer over a rectangle. This will show you the CSS for the element you point at.
5. Now move your pointer to the context menu item whose ID you want to find out. It should get highlighted with a red border.
6. Switch back to the Browser Toolbox. The left hand pane should have a selected entry. You can right click > copy > CSS Selector to get the right selector.

You can use this way to get the CSS selector for every element of the browser you want to style or hide.
  

___

To **remove entries from the context menu** you need to 

1. [Create userchrome.css](http://kb.mozillazine.org/index.php?title=UserChrome.css&printable=yes) if you haven't already
2. Open the userchrome.css for your current profile with a text editor.
3. Write an entry with your CSS selectors (separated by commas) and hide them. 

Like so

    #context-navigation, #context-sep-navigation { 
        display: none !important 
    }
  
___
To **change the position of a context menu entry** you have to:

Give the item you want on the very top a `-moz-box-ordinal-group: 0`, without doing anything for any other item.

This example will put the search of selected text on top of the context menu.


    #context-searchselect {
        -moz-box-ordinal-group: 0 !important;
    } 


If you want to move an item to the very bottom, use `-moz-box-ordinal-group: 2` (or any number >1), again, without doing anything for any other item.  
  
If you want to move multiple items to the very bottom, then give only these items increasing `-moz-box-ordinal-group` e.g. 2, 3, 20 and so on. The highest number will be at the bottom. If you give all of these the same number, then while they will stick together at the bottom, they might rearrange amongst themselves depending on when and how they are being added / removed.

You could give each menu entry a distinct ordinal number to exactly put them where you want them but I found I only really needed to move my context search to the top of the menu for maximum convenience.

___
Thanks and credit to u/BatDogOnBatMobile  for his comment [here](https://www.reddit.com/r/firefox/comments/76tkwp/userchromecontext_menu_help/dogrfss/) that inspired this post
