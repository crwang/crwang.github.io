---
permalink: "/cheatsheets/sublime-text/"
layout: page
title:  "Sublime Text Cheatsheet"
---

<ol class="breadcrumb">
  <li><a href="/cheatsheets">Cheatsheets</a></li>
  <li>Sublime Text</li>
</ol>

## Recommended Settings

### Rails

Set indentation to 2

### Node.js

### Handlebars Templates

## Sublime projects

A great way to use Sublime as more of an IDE is to enabled the sidebar view, to drag the folder into the sidebar so you have a crude Finder/Explorer view and then to save as a project.

## Recommended Sublime Text plugins

### Handlebars

[https://github.com/daaain/Handlebars](https://github.com/daaain/Handlebars)

1.  Press Shift + Command (or Control) + P
2.  Type "install", to bring up the "Package Control: Install Package" option, and press Enter
3.  Look for "Handlebars", and press Enter to install it.
4.  Choose "Handlebars" in the bottom right corner with one of your template files open (or in case you have inline templates use Handlebars instead of HTML, it's gracefully extending it so you shouldn't lose anything)
5.  Open an .hbs file and make sure to select Handlebars on the bottom right of the Sublime Text Editor

## Markdown Editing

[https://sublime.wbond.net/packages/MarkdownEditing](https://sublime.wbond.net/packages/MarkdownEditing)

1.  Install Sublime Package Control
2.  From inside Sublime Text, open Package Control's Command Pallet: CTRL SHIFT P (Windows, Linux) or CMD SHIFT P on Mac.
3.  Type install package and hit Return. A list of available packages will be displayed.
4.  Type MarkdownEditing and hit Return. The package will be downloaded to the appropriate directory.
5.  Restart Sublime Text to complete installation. Open a Markdown file and this custom theme. The features listed above should now be available.
6.  Open an .md file and make sure to select Markdown on the bottom right of the Sublime Text Editor

### Html/CSS/JS prettify

[https://sublime.wbond.net/packages/HTML-CSS-JS%20Prettify](https://sublime.wbond.net/packages/HTML-CSS-JS%20Prettify)

1.  Ctrl+Shift+P or Cmd+Shift+P in Linux/Windows/OS X
2.  type install, select Package Control: Install Package
3.  type prettify, select HTML-CSS-JS Prettify

### Beautify Ruby

[https://github.com/CraigWilliams/BeautifyRuby](https://github.com/CraigWilliams/BeautifyRuby)

### Ruby Tests (RubyTest)

[https://github.com/maltize/sublime-text-2-ruby-tests](https://github.com/maltize/sublime-text-2-ruby-tests)

#### Set up for RVM

Sublime -> Preferences -> Package Settings -> RubyTest -> Settings (User/Default)

```
{
  "check_for_rvm": true,
  "check_for_bundler": true
}
```

#### Set up for Ruby Install/chruby

Sublime -> Preferences -> Package Settings -> RubyTest -> Settings (User/Default)

https://github.com/maltize/sublime-text-2-ruby-tests/issues/188

```
{
  "run_ruby_unit_command": "source /usr/local/opt/chruby/share/chruby/chruby.sh && chruby 2.1.6 && ruby -Itest {relative_path}",
  "run_single_ruby_unit_command": "source /usr/local/opt/chruby/share/chruby/chruby.sh && chruby 2.1.6 && ruby -Itest {relative_path} -n '{test_name}'",
  "run_rspec_command": "source /usr/local/opt/chruby/share/chruby/chruby.sh && chruby 2.1.6 && rspec {relative_path}",
  "run_single_rspec_command": "source /usr/local/opt/chruby/share/chruby/chruby.sh && chruby 2.1.6 && rspec {relative_path}:{line_number}",
}
```

### Spaces and new lines

[https://github.com/sindresorhus/editorconfig-sublime](https://github.com/sindresorhus/editorconfig-sublime)

### Git help

[https://github.com/jisaacks/GitGutter](https://github.com/jisaacks/GitGutter)

### JSHint

#### Installation

1.  Install sublime linter. `https://github.com/SublimeLinter/SublimeLinter3`
2.  Install node's jshint `npm install -g jshint`
3.  Then, install sublime linter for jshint. `https://github.com/SublimeLinter/SublimeLinter-jshint`

#### AirBnb's linter.

[https://github.com/airbnb/javascript/blob/master/linters/SublimeLinter/SublimeLinter.sublime-settings](https://github.com/airbnb/javascript/blob/master/linters/SublimeLinter/SublimeLinter.sublime-settings)

### Zen Tabs

Provide a more intuitive approach for going through tabs.  Similar to Notepad++ and Visual Studio.

https://github.com/travmik/ZenTabs

### Highlight

Provides functionality to copy as html/rtf.  This is useful for me as a way to copy code and paste it into my notes program (currently OneNote).

https://github.com/n1k0/SublimeHighlight

## Customization

### Color Settings

To set the colors for different projects you can go to:

Project -> Edit Project

And add the settings json for color_scheme.

I recommend doing this when you have multiple projects that you may be working on. For me, I'll do this when I have a predominantly Rails project and predominantly Node project that connect. It makes it much easier to context switch for me.

Example:

    {
        "folders":
        [
            {
                "follow_symlinks": true,
    //            "folder_exclude_patterns": ["node_modules"] // for node projects
                "path": "web"
            }
        ],
        "settings":
        {
            "color_scheme": "Packages/Color Scheme - Default/Cobalt.tmTheme",
            "draw_white_space": "all",
            "trim_trailing_white_space_on_save": true
        }
    }

## Keyboard commands

Goto Anything

Use Goto Anything to open files with only a few keystrokes, and instantly jump to symbols, lines or words.

Triggered with ⌘P, it is possible to:

Type part of a file name to open it.
Type @ to jump to symbols, # to search within the file, and : to go to a line number.
These shortcuts can be combined, so tp@rf may take you to a function read_file within a file text_parser.py. Similarly, tp:100 would take you to line 100 of the same file.

## Mac OS - Run from Terminal

Slightly modified from https://www.sublimetext.com/docs/3/osx_command_line.html to put the symlink in `/usr/local/bin` instead of `~/bin`

Previously, it was ok to use `/usr/bin` but from El Capitan (rootless mode) that is no longer permitted.  There are ways to disable it but it's better to just use `/usr/local/bin` now.

```bash

sudo ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" /usr/local/bin/subl

```

