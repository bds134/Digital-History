# Visual Studio Code, Command Line Interface, and Markdown Basics

In this lesson, you will learn some basic tools that allow you do practice minimalist computing.

## Visual Studio Code

An Integrated Development Environment (IDE) is a place where you can write, push, and pull code. Visual Studio Code is a free IDE that is now owned and managed by Microsoft. It is also a wonderful text editor and file management system that can handle everything that a Historian needs. You can write rich text documents; manage files and directories (i.e. folders); view images and combine them with text; write basic code for a number of languages to manage any public (or private) websites or webpages; compose, edit and manage tabular data, be they in 'flat' sheets or relational databases; practice version control through connectivity with sites such as GitHub; and manage servers and server-hosted databases. Best of all, VSC offers an interface that is free of many graphical distractions, letting you focus on writing.

### Installation & Basics

- Start with the [VSC Basics page](https://code.visualstudio.com/docs/introvideos/basics)
- Install via [Download Visual Studio Code](https://code.visualstudio.com/download)
- Open a folder
  - File > Open Folder (Ctrl+K Ctrl+O)
  - VSC creates workspaces based upon this 'open folder' command

### VSC Tour

- split into new editor/viewer to left/right/down/up
- preview (ctrl+k+v)
- ctrl+tab -> change active document

#### Vertical Activity Bar (left-hand side)

- Explorer
- Search tool
- Source control
- Run and debug
- Extension marketplace
- Accounts
- Manage settings
- Outline
- Timeline

#### Command Palette

Important tool (ctrl+p) to find and run commands for VSC.

#### Status Bar

- info about current doc

#### Utility Panel

- output
- debug
- problems
- terminal

#### New Document

- ctrl+n
- right-click directory in explorer

#### VSC Options

- intellisense will kick in
- some languages do not have native intellisense; look at extensions fefe
- unsaved changes indicated with 'dot'
- yellow error messages (visible in-doc and at bottom)
- map column on right of doc
- ctrl+shift+p -> command palette -> e.g. "color theme"

## Command Line Interface

Method of interacting with your computer without GUI. Often simplified workflow with unambiguous results that produce a scripted history of what you did.

Accessible through Command Line (or Powershell) on Windows and Terminal on Mac.

Or accessible in VSC.

### Two great resources

- Powershell (Windows) [Introduction to the Windows Command Line with PowerShell](https://programminghistorian.org/en/lessons/intro-to-powershell)
- Bash (Linux/Mac) [Introduction to the Bash Command Line](https://programminghistorian.org/en/lessons/intro-to-bash)

### Basic syntax

- [command] [argument(s)] [options/flags]
- cmdlet = command
- arguments = a value that is passed between programs, subroutines or functions
- options = parameters = `-[option]` change the mode of cmdlet
- flag = like an option/parameter except they act as toggle switches for cmdlet mode

### Basic cmdlets

*Cmdlets should be entered literally, except when:

- a slash separates commands (e.g. ni / touch), in which case powershell users should use the first cmdlet (e.g. 'ni') and bash users the second (e.g. 'touch')
- square brackets are used, in which case the brackets and contents of the brackets should be replaced by the referenced item (i.e. 'ls [path or omit for current directory]' should be written as 'ls /assets/)

Basic cmdlets:

- List contents of directory `ls [path or omit for current directory]`
- Curent directory `.`
- Home directory `~`
- Change directory `cd`
- go backwards in file tree `cd ..`
- Add directory `mkdir [path]`
- Add file `ni / touch`
- Remove file or directory `rm [path]`
- Move or rename `mv [path-from] [path-to]`
- Copy item `cp [path-from] [path-to]`
- Read file `gc [path]`
- Open in VSC `code / open [path]`
- Reveal in explorer `explore [path] / open [path]` (if path is a directory, will launch Explorer or Finder; if path resolves to file, will launch the default program for that file extension)
- Get help `get-help [cmdlet]` or `get-help -online [cmdlet]`

### Other tricks

- Tab key to cycle through autocomplete options
- Shift-tab too reverse cycle through autocomplete options
- Browse the history of commands with ARROW Keys
- \ = /
- 'to' default to current directory (i.e. working directory)
- Do not add spaces to names of directories or files; instead, use dashes, underscores, or capitalization to distinguish between words

### CLI Mini-Exercise

1. Create a file tree for this class with directories and Markdown notes files. NB: Create multiple directories and files by separating new items by comma
2. Open today's notes file in VSC by initiating in CLI
3. Make a test.txt file.
4. Rename test.txt to test2.txt.
5. Copy test2.txt to test.txt.
6. Create "test" directory.
7. Move test.txt and test2.txt to "test" directory.
8. Delete both test.txt and test2.txt.
9. Delete "test" directory.
10. Create "assets" directory.

## Markdown

VSC provide native md.

Recommend adding extension "markdownlint".

### General rules

- each md doc needs one and only one first-level header (`#`)
- add blank line before and after paragraph with new format type
- no space at end of line (unless two spaces)
- blank line at end
- no punctuation at end of headings

### [Basic syntax](https://www.markdownguide.org/cheat-sheet/)

- headings `#, ##, ###` -> h6 `######`
- italic `*...*`
- bold `**...**`
- blockquote `>` no space after \>

### Lists

There are two types of lists, unordered and ordered.

For unordered (bulletted) lists, begin with a hyphen and a space, e.g. `-_` (the space is represented here as an underscore to make it explicit). If you have Markdown All-in-One extension for VS Code installed (yzhang.markdown-all-in-one), new bulletted items will be created automatically.

To create an ordered list, add line items with numbers followed by periods `1._`. The numbers don’t have to be in numerical order, but the list should start with the number one.

```markdown
1. First item
2. Second item
3. Third item
4. Fourth item
```

This is rendered as:

1. First item
2. Second item
3. Third item
4. Fourth item

Or even when composed with non-sequential or repeated numbers, it renders well.

```markdown
1. First item
8. Second item
3. Third item
5. Fourth item
1. Fifth item
```

This will render as:

1. First item
8. Second item
3. Third item
5. Fourth item
1. Fifth item

### Links to urls & images

You can make links to images or to resources such as documents or webpages. Either can be located online or in local storage. The basic structure is [description](location "hover-over text"), with the hover-over text being optional.

For url links, it looks like this:

>links `[title](path or url"optional hover text")`

For images, the title is is preceded by a !, such as:

>images `![alt text](path or url)"optional hover title"`

The tricky part is providing valid file paths for local files and, less so, valid urls for web resources. I have create a document with [examples of paths and urls in Markdown](examples-links-markdown.md)

### Code

- in-line code `[code here]`
- block code

```markdown
[code here]
```

### Tables

```markdown
| column1 header | column2 header |
| --- | --- |
| r1c1 value | r1c2 value |
| r2c1 value | r2c2 value |
```

### Two Markdown Mini-Exercises

1. Grab some research notes from a file (Word or Google Doc) and paste it into a Markdown file that you create. Format the document to make various headings, bullet points, quotes, etc. Remove all errors.
2. Take notes using Markdown for the remainder of the class! Add any image to your "assets" directory. Use Markdown syntax to show the image in the md document.

### Sustainable Authorship in Plain Text using Pandoc and Markdown

Here is an **optional** tutorial for [Sustainable Authorship in Plain Text using Pandoc and Markdown](https://programminghistorian.org/en/lessons/sustainable-authorship-in-plain-text-using-pandoc-and-markdown)

## Regex

>Regular expressions provide a powerful, flexible, and efficient method for processing text. The extensive pattern-matching notation of regular expressions enables you to quickly parse large amounts of text to:
>
>- Find specific character patterns.
>- Validate text to ensure that it matches a predefined pattern (such as an email address).
>- Extract, edit, replace, or delete text substrings.
>- Add extracted strings to a collection in order to generate a report.
>
>For many applications that deal with strings or that parse large blocks of text, regular expressions are an indispensable tool.

- [Regex Playground and Learning Tools](https://regex101.com/). For instance, look at the [Regex Quiz](https://regex101.com/quiz)
- VSC has its own 'flavor' of regex that has a few quirks vis-a-vis the "standard" regex. [Look at this page for help with regex in VSC](https://learn.microsoft.com/en-us/visualstudio/ide/using-regular-expressions-in-visual-studio?view=vs-2022)

### Regex basic syntax

- escape key `\`
- any character `.` ["Match any single character (except a line break)"]
- any `*` ["Match zero or more occurrences of the preceding expression (match as many characters as possible)."]
- multiple any character `.*` ["Match any character zero or more times."]
- beginning of line `^` ["Anchor the match string to the beginning of a line or string"]
- end of line `$`
- carriage return `\r`
- new line `\n`
- carriage and new line `\r\n`
- any word character `\w`
- not a word character `\W`
- any space `s`
- not a space `S`
- any decimal number `\d`
- any tab character `\t`
- word beginning or end `\b`

### Use regex to make a table in markdown

1. Use CLI to make file called "CLI-quickreference.md". We will need this new file to be opened in a VSC editor, which can be accomplished by either clicking on the file in the 'Explorer' tool or by using the CLI (type "code CLI-quickreference.md")
2. Give the new *.md file a first-level heading (i.e. \#)
3. Go to [Introduction to the Windows Command Line with PowerShell](https://programminghistorian.org/en/lessons/intro-to-powershell).
4. Copy and paste all text from the section called "Quick Reference" section to the new file we created.
5. Now let's get to work replacing text. Remember that a 'table' in Markdown uses pipes to separate fields and needs the second row (i.e. the one after the header row) to have the pipes separated by three dashes, like this: `| --- | --- |`, one for each column you wish to create.
6. Select the pasted text and use 'select mode' in Replace tool
7. To format the internal column divisions, "Replace" `\t` with `_|_` (underscores = spaces; i.e. ensure spaces around the pipe)
8. To format first pipe of each line, "Replace" `^` with `|_` (ensure space **after** the pipe)
9. To format last pipe of each line, "Replace" `\r?\n` or `$` with `_|`
10. Add (manually w/o regex) table structure to second row: `| --- | --- |` ... etc
11. Review your work. Any problems?
12. Correct third last line (i.e. line 20) which has pipes. Use the escape character `\` before the "literal" pipes
