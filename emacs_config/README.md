# My Emacs Configuration :sunrise:

# Contact
- **Email me if there are any issues/questions/things that can be better**: marin.marinov@macaulay.cuny.edu

# Table Of Contents
- [Notes Before Beginning](#Notes-Before-Beginning)
- [Possible Issues](#Possible-Issues)
- [Themes I use](#Favorite-Themes)
- What Packages Are In My Init File:
  - [For Vim users](#Vim)
  - [Start-up Screen Packages](#Start-up)
  - [Productivity Packages](#Extra-Productivity-Helper-Packages)
  - [Mode Line Packages](#Modeline-Customization)
  - [Enhance Emacs packages](#Emacs-enhancements)
  - [Shell Packages](#Shell)
  - [Global Packages](#Global-Emacs-Helpers)
  - [Project Management Packages](#Project-Management)
  - [General Coding Packages](#Coding-Productivity)
  - [Github package](#GitHub-Integration)
  - [Org & MarkDown packages](#Org-and-Markdown)
  - [C++ packages](#Cpp)
  - [Python packages](#Python)
  - [JavaScript packages](#JavaScript)
  - [Web-Development packages](#Web-Development)
  

## :loudspeaker: IMPORTANT:  
- I use init.el and marinmacs.org to run my emacs! The [.emacs](https://github.com/marinov98/My_Emacs-Detailed_Guide/blob/master/emacs_config/backup/.emacs) file in the backup folder is an old version of my init file without utilizing org mode and use-package
- **Make sure** you read the previous [README](https://github.com/marinov98/My_Emacs-Detailed_Guide/blob/master/README.md) before proceeding with this part of the guide.

# Things to consider as you customize your emacs

## Notes-Before-Beginning
- Any errors you get can be googled and every package can also be checked online 
- Depending on how you installed emacs, certain packages might be preinstalled into it 
- When you see ```RET``` it means hit the ENTER key
- In emacs C = ctrl and M = alt 
- Example: ```M-x``` = alt + x  ```C-x C-f``` = ctrl + x ctrl + f
- If you wish to browse through Emac's packages ```M-x package-list-packages RET``` will open up the package list
- Additonally you can run ```M-x package-install RET package_name RET``` if you know the exact package that you want 
- If you just want to get it over with, simply copy my ```init.el``` and ```marinmacs.org```(or whatever you want to name your org file) the files should be created inside the ```.emacs.d``` folder which you can create. All the packages should install and configure automatically (power of use-package), **however** you would still have to install the servers for jedi(Python) and irony(C++) (instructions for that below)

# Possible-Issues 
- After installing my config on a few different machines, I encountered some minor bugs, but they are easily fixed
- They are rare but they still happen so here are some solutions to them 
## Issue #1: Package cannot load 
- **Possible Solution** run ```M-x package-refresh-contents ``` , if that doesnt work and the package doesnt mean much to you, remove it from the config or look up the package to see if anything has changed, some packages get deleted over time or replaced or become native to emacs and do not to be specified in the config
## Issue #2 : (some word) is void 
- **Possible Solution #1 :** my config is tested, so there should not be anything that stops your emacs file from loading, however sometimes because my config has long lines of code and emacs default size is not that big, emacs indents and the piece of code goes on a new line and is not part of anything so it looks like an error 
- Best thing to do is ```C-s``` and search for the word and either try to put it in the same line or delete it
- **Possible Solution #2 :** Make sure you have my init.el copied (fix any small indentention issues there) then run ```M-x customize RET```, go to faces->basics faces->default change the size of the emacs screen to prevent it from indenting.

## Favorite-Themes

### Base16 (Contains 20+ themes but these are my top picks)
- base16-ocean 
- base16-oceanicnext 
- base16-tomorrow-night
- base16-solarized-dark/light

### Colorful and visually pleasing    
- Spacemacs-theme
- Zerodark

### Easy on the eyes
- Gruvbox
- Zenburn
- JellyBeans 
- Planet
- solarized-dark (from solarized-theme NOT base16)

### For Org and any Markdown Language
- Poet

# What My Init File Consists Of (Currently)

## General Settings 
- set tab to 4 spaces
- force editor to use spaces
- syntax highlighting
- debugging on error 
- tool bar turned off
- Disable annoying backup files

# Packages

## Use-Package 
- ```use-package``` (provides the use-package syntax and makes emacs download files if they are not intalled yet)
## linum-relative & restart-emacs
- the ```restart-emacs``` package allows use to keybind the command ```restart-emacs``` so that we can restart and refresh the session with one keystroke whenever we need to.
- ```linum-relative``` enables relative line numbering. 
- If you want normal line numbers, comment linum-relative and put ```(global-linum-mode 1)``` instead

## Vim 
- **WARNING** You need undo tree for this package to fully work (if you are copying my entire config this is not a problem)
- Any **movement keybindings** in the Personal Keybindings section of my init will be disabled once evil is uncommented
- If you just want **Emacs keybindings** either erase any "evil" package or comment them 
#### Packages for Vim: 
- **You have to make sure this package is NOT commented in order to ENABLE THE BINDINGS:**
  - evil (basically creates vim inside emacs) 
- **Evil support packages:**
  - evil-surround (just like surround in vim)
  - evil-mc (vimlike multiple cursors)

## Start-up
- dashboard (customizable start up screen)


## Extra-Productivity-Helper-Packages
- which-key (key assignments help)
- ace-window (faster window swapping)

## Modeline-Customization 
- Pick one:
  - telephone-line (currently enabled)
  - spaceline
  - powerline 

## Emacs-enhancements
- Debug on multiple-windows
- ranger (ranger-like file manager, replaces dired)
- avy (fast word navigation)
- **Ivy Integration**
  - ivy (Tool for managing (recording, tracking, resolving and reporting) project dependencies.)
  - swiper (improved file/name search by integrating ivy)
  - counsel (enhanced ivy commands)

## Shell
- better-shell (improves shell functionality within emacs)
- exec-path-from-shell (sets paths for the terminal automatically)

## Global-Emacs-Helpers
- auto-complete (convenient global auto-completion within emacs)
- yasnippet, yasnippet snippets (snippets)
- company (auto-completion)
- flycheck (linter/syntax checker)
- undo-tree (smarter undo)

## Project-Management
- projectile (Project interaction library for emacs)
- counsel-projectile (ivy integration of projectile)

## Coding-Productivity
- beacon (light that follows your cursor)
- all-the-icons (provides icon-images)
- neotree (popup sidebar for easy directory/file navigation)
- Multiple-cursors (create multiple cursors on one screen)
- iedit (change multiple words at the same time)
- dump-jump (jump to definition) 
- cider (interactive programming with clojure)

## GitHub-Integration 
- magit 

## Org-and-Markdown
- org-bullets (prettier org formatting)
- auctex & tex(smoother latex editing)
- pdf-tools (pdf support in emacs)
- wc-mode (word counter)
- writegood-mode (sentence/word choice checker)

## Cpp
- c++-modern-font-lock (helpes emacs recognize c++11 and above)
- clang-format (formats c++ code)
- irony (C++ minor mode based on libclang works with company to give intellisense)
- company-irony (provides true intelligent c++ intellisense and autocompletetion)
- company-irony-c-headers (auto completetion for header files)
- irony-eldoc (indexes c++)
- flycheck-irony (C/C++/obj-C syntax checker)
- ggtags (creates tags where you jump around and navigate to definitions)
#### C++ Irony-server:
- Run ```M-x irony-install-server RET``` after you put company-irony in your init file(will only execute if you have cmake and libclang installed!). You now have C++ intellisense :D

## Python
- virtualenv (interactive python shell) 
- virtualenvwrapper (virtualized isolated python environment)
- elpy (enables a powerful python development environment)
- company-jedi (intellisense)
#### Python Jedi Server:
- Run ``` M-x jedi:install-server RET``` AFTER you added company-jedi to your init file AND AFTER you installed pip installed virtualenv. Now you have Python intellisense ;)

## JavaScript 
- js2-mode (enables Javascript mode in emacs)
- js2-refactor (powerful refactoring)
- xref-js2 (easy jumping to definitions and refrences)
- company-tern (Javascript intellisense)
- add-node-modules-path (sets proper path for modules)

## Web-Development 
- web-mode (allows for auto completion and automatic tag closing) 
- skewer (live web development)
- emmet-mode (increase html/css productivity with snippets) 


