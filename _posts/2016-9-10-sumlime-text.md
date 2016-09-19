---
layout: inner
title: 'Sublime Text 3'
date: 2016-9-10 13:26:34
categories: blog development
tags: Sublime Text 3
lead_text: 'Becoming a sublime power user'
---


#There are my personal collection about Sublime Text 3


##Shortcuts

1. The shortcut to show or hide the side bar is `Ctrl+K`, `Ctrl+B` (Mac: `Cmd+K`, `Cmd+B`). `Up/Down Arrow Keys` Move up/down the side bar when it has the focus. `Left/Right Arrow Keys` Expand and collapse folders when the side bar has the focus. `Esc` Return the focus to the active view.
2. You can open Goto Anything with `Ctrl+P` (Mac: `Cmd+P`).
3. To open the Command Palette, press `Ctrl+Shift+P` (Mac: `Cmd+Shift+P`).
4. Full screen mode, press `F11` (Mac: `Cmd+Ctrl+F`).
5. To enter or exit distraction-free mode, press `Shift+F11` (Mac: `Cmd+Shift+Ctrl+F`). A shortcut that marries well with distraction-free mode is `Ctrl+K`, `Ctrl+C`. 
6. To see the current scope, press `Ctrl+Alt+Shift+P` (Mac: `Cmd+Alt+P`). 
7. To show or hide the console, press `Ctrl+``.
8. To create a new, unsaved file, press `Ctrl+N` (Mac: `Cmd+N`).
9. To close a file, press `Ctrl+W` (Mac: `Cmd+W`). 
10. To switch between projects, you can use the keyboard shortcut `Ctrl+Alt+P` (Mac: `Cmd+Alt+P`), which opens the Quick Switch Project feature. Before you can start switching between projects, however, you must have already opened at least two different projects.
11. To open Goto Anything, press `Ctrl+P` (Mac: `Cmd+P`). 
12. To go to a specific line in the active file, use the ‘:’ operator (also: `Ctrl+G`):
13. To perform a fuzzy search on the active file’s content, use the ‘#’ operator (also: `Ctrl+;`; no shortcut available for Mac):
14. To find a specific symbol in the active file, you can use the ‘@’ operator (also: `Ctrl+R`; Mac `Cmd+R`):
15. All these operators can also be used after a file name to target that file instead of the active file.('filename'#h)
16. To switch between the most recent two files, you can simply press `Ctrl+P` (Mac: `Cmd+P`), then Return. That’s fast and convenient once you get used to Goto Anything, and probably easier than reaching for the alternative `Ctrl+Tab`.
17. Switch between recent tabs, `Ctrl+Tab` for both Windows and Mac; Go to next/previous tab, `Ctrl+PgDown/PgUp` for Windows( `Cmd+Shift+[/]` for Mac).
18. There are a number of keyboard shortcuts devoted to managing groups of views:

  ```
  For Windows:
  
  Ctrl+K, Ctrl+Up	Move file to new group
  Ctrl+K, Ctrl+Down	Close group
  Ctrl+K, Ctrl+Left	Focus previous group
  Ctrl+K, Ctrl+Right	Focus next group
  Ctrl+1–9	Focus numbered group
  Ctrl+Shift+1–9	Send files to numbered group
  
  For Mac:
  
  Cmd+K, Cmd+Up	Move file to new group
  Cmd+K, Cmd+Down	Close group
  Cmd+K, Cmd+Left	Focus previous group
  Cmd+K, Cmd+Right	Focus next group
  Cmd+1–9	Focus numbered group
  Ctrl+Shift+1–9	Send files to numbered group
  
  ```

19. Here are the keyboard shortcuts to activate some of these available layouts:
  
  One-Column layout (Default):`Alt+Shift+1`(Mac:`Cmd+Alt+1`);Two-Column layout:`Alt+Shift+2`(Mac:`Cmd+Alt+2`)
20. Sometimes it’s useful to simultaneously take a look at two different parts of the same file. Click on “File,” then “New View into File”.
21. Folding sh

  ```
  Ctrl+Shift+[	Fold
  Ctrl+Shift+]	Unfold
  Ctrl+K, Ctrl+0	Unfold All
  Ctrl+K, Ctrl+1	Fold All
  Ctrl+K, Ctrl+2	Fold Level 2
  Ctrl+K, Ctrl+3	Fold Level 3
  
  For Mac:
  
  Alt+Shift+[	Fold
  Alt+Shift+]	Unfold
  Cmd+K+0	Unfold All
  Cmd+K+1	Fold All
  Cmd+K+2	Fold Level 2
  Cmd+K+3	Fold Level 3
  
  ```

22. Keyboard Shortcuts Related to Bookmarks:

  ```
  Ctrl+F2	Set a bookmark
  Ctrl+F2	Remove a bookmark
  Ctrl+Shift+F2	Remove all bookmarks
  Alt+F2	Select all bookmarks
  F2	Travel to next bookmark
  Shift+F2	Travel to previous bookmark
  
  For Mac:
  
  Cmd+F2	Set a bookmark
  Cmd+F2	Remove a bookmark
  Cmd+Shift+F2	Remove all bookmarks
  Alt+F2	Select all bookmarks
  F2	Travel to next bookmark
  Shift+F2	Travel to previous bookmark
  
  ```

23. You can trace back your steps as you work through a project by pressing `Alt+-` on your keyboard. This shortcut will teleport you to locations you’ve visited recently, across all your open files. To move forward in the series, press `Alt+Shift+-`. 
24. To open the local list, press `Ctrl+R`. To open the global list, press `Ctrl+Shift+R`.
25. 

##Setting 

1. The main types of settings are global settngs, view settings, syntax-specific settings, project settings, and folder settings.
2. Order of precedence for loading settings:
  * Packages/Default/Preferences.sublime-settings
  * Packages/Default/Preferences (<platform>).sublime-settings
  * Packages/User/Preferences.sublime-settings
  * <Project Settings>
  * Packages/<syntax>/<syntax>.sublime-settings
  * Packages/User/<syntax>.sublime-settings
  * <Buffer Specific Settings>

Note that Packages/Default includes the Default.sublime-package package even though this package isn’t physically located there.

3. Global settings are stored in the Preferences.sublime-settings file.There are two important global setting files: the Default Preferences file, and the User Preferences file.To change global settings, use the User Preferences file. 
4. The syntax definition files in Sublime Text may have the .tmLanguage or the .sublime-syntax extension. 
5. Settings for the Distraction-Free mode are located in Distraction Free.sublime-settings.
6. To enable rulers, choose rulers in your User Preferences file. Indicate where you want your rulers to be drawn by typing their locations as a list of integers using the JSON syntax (for example, `"rulers":[80, 120]`) representing how many characters from the left the ruler will fall. 
7. The `tab_size` setting determines the width of a tab character measured in spaces; 4 and 2 are both common values. When `translate_tabs_to_spaces` is set to true, the given number of spaces will be inserted in place of the tab character.
8. The tidy `trim_trailing_white_space_on_save` setting automatically removes extraneous spaces from the end of lines when you save a file, which is generally desirable. However, some files expect these spaces to be preserved, so this setting may cause problems for certain projects.
9. The `ensure_newline_at_eof_on_save` instructs Sublime Text to automatically add a newline character at the end of a file when you save it.
10. The `caret_style` controls the appearance of the caret.
11. The `theme` setting determines the look of the UI.
12. You can change the `color_scheme` by adding the path to the color scheme manually, or you can click on “Preferences” and then “Color Scheme,”and find a color scheme there.
13. The `show_encoding` setting shows the current file’s encoding in the status bar.
14. To show the active file’s line terminator (also known as the line ending) in the status bar, use the `show_line_endings` setting. 
15. To ignore and hide folders from projects, use the `folder_exclude_patterns` setting
16. To ignore and hide files from projects, use the `file_exclude_patterns` setting
17. The `binary_file_patterns` setting ignores files while performing project-wide actions (like searching), but does not hide the files.
18. Use `always_show_minimap_viewport` make the minimap viewport always visible. Otherwise, it is only visible when you hover the mouse over the minimap.
19. The `draw_minimap_border` draws a border around the visible rectangle on the minimap. To enable this setting, `always_show_minimap_viewport` must also be enabled.
20. This, `ignored_packages`, is a list of packages that Sublime Text will ignore. Ignored packages will not be available for use. If a package you use stops working, check first whether you’ve added it to `ignored_packages`.
21. The `highlight_line` setting highlights the active line.
22. The `highlight_modified_tabs` setting highlights modified tabs in a different color so they stand out more.
23. By default, if you restart Sublime Text while in full-screen mode, you’ll return to normal-screen mode. This default setting is intended to make it easy to return the desktop. If you are going to use the full-screen mode often, you may want to change this setting in your User Settings file using `remember_full_screen`, which makes Sublime Text remember the full-screen state.
24. You’ll generally edit a `.sublime-project` file in order to add project-specific settings and folder settings. To open the project file for editing, click on “Project” and then “Edit Project” in the main menu.
25. Project-specific settings are added under the top-level “settings” key. If this key isn’t present, you can create it yourself. Here’s an example of a file setting that will only be in effect for files in the corresponding project:

   ```
  
    "folders": [
        { "path": "." }
    ],

    "settings": {
        "trim_trailing_white_space_on_save": true
    }
  
  ```

26. Folder settings are added directly under each folder’s entry in the .sublime-project file and are designed to affect those parts of the editor that are related to the management of projects. For example, if you exclude files from a folder, those files will not be available in the side bar, in Goto Anything or in project-wide searches. 

  ```
   "folders":
     [
         {
             "path": ".",
             "file_exclude_patterns": ["*.exe"]
         }
     ],
 
     "settings": {
         "trim_trailing_white_space_on_save": true
     }
  
  ```
  
  ```
  
	"folders":
  	[
    		{
    			"path": ".",
    			"folder_exclude_patterns": ["vendor", "dist"]
    		}
  	]
  
  ```

27. Whenever you create a `.sublime-project` file, a corresponding `.sublime-workspace` file will be generated as well. The former may be safely committed to a source code repository. The latter, however, should never be as it contains many project details and is used by Sublime Text to keep track of the state of the project.

 Note: Never commit `.sublime-workspace` files to a source code repository. They may contain sensitive data. 
 
28. Sublime Text `.sublime-workspace` files have another purpose in addition to storing details about the state of a project. They can also be used as subprojects. You can create separate workspaces in order to switch between files while remaining in the same project. 
29. Common Folder Settings
 * folder\_exclude\_patterns: Any patterns listed here will exclude matching folders from the side bar and project-wide actions, like Goto Anything and project searches.
 * folder\_include\_patterns: Any patterns listed here will make matching folders the only ones available in the side bar and project-wide actions, like Goto Anything and project searches.
 * file\_exclude\_patterns: Any patterns listed here will exclude matching files from the side bar and project-wide actions, like Goto Anything and project searches.
 * file\_include\_patterns: Any patterns listed here will make matching files the only ones available in the side bar and in project-wide actions like Goto Anything and project searches.
 * binary\_file\_patterns: Any patterns listed here will make matching files visible in the side bar, but they will be excluded from the side bar and project-wide actions, like Goto Anything and project searches.
30. 

 
  
  
##Debugging

1. It can sometimes be helpful to check which settings are being applied to the current file.`view.settings().get('<some_setting_name>')`, `view.settings().get('syntax')`

 For example, `view.settings().get('tab_size')`
2. If you are dealing with a global setting, this is the correct incantation:`window.settings().get('<some_setting_name>')`
3. To set a setting from the console, you can use one of these two statements:

  `view.settings().set('<setting_name>', <setting_value>)`
  `window.settings().set('<setting_name>', <setting_value>)`
  
  For example, `view.settings().set('translate_tabs_to_spaces', False)`

Note: If you don’t know whether a setting is a view or a global setting, you can try both ways and see which one returns a value.

##Packages

1. There are two main files containing keyboard shortcuts: the Default.sublime-keymap file — located in the Default.sublime-package — and the Default (<platform>).sublime-keymap file. The latter is located in your Packages/User directory.
2. Sublime Text setting files use the JSON format, and they have a .sublime-settings extension (for example, Preferences.sublime-settings).
3. A Sublime Text project is defined in a JSON configuration file with the .sublime-project extension as following:
  ```
   {
        "folders": [
            {
                "path": "."
            }
        ]
    }
    
  ```


##Where to ask help?

1. [official forum](https://forum.sublimetext.com)
2. [Unofficial Documentation](http://docs.sublimetext.info/en/latest/index.html)
3. [official help pages](http://www.sublimetext.com/docs/3/)




