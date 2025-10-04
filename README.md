# Auto Comment Blocks

Provides block comment completion for Javadoc-style multi-line comments and single-line comment blocks for most officially supported languages.

### Single-line Comment Blocks
You can now use single line comment blocks for languages with `//` style single line comments. Press `Shift+Enter` while on a commented line to insert a new commented line with the same level of indentation. See the Settings section for how to change the behavior so that `Enter` inserts a commented line while `Shift+Enter` breaks out of the comment block (this only works correctly for a subset of languages right now).

The Language Support section shows which languages are supported. See the Settings section for how to add single line comment support to languages that are not officially supported.

### Multi-line Comment Blocks
This feature has not changed.

### Javadoc-style comment blocks
Type `/**` to start a block comment, then hit the Enter key, and the extension will close the block. While inside the comment block, the extension will insert an asterisk at the start of every new line, and align the comment, respecting indentation.

### QDoc-style (Qt) comment blocks
Use `/*!` in DM files to start a comment block.

### single-line block comments
You can insert single line comment blocks for languages with `//` style single line comments. Press `Shift+Enter` while on a commented line to insert a new commented line with the same level of indentation. See the Settings section for issues and more options.

### Language Support

| Comment Style | Language Support |
| ------- | ------- |
| `/** */` | DM |
| `/*! */` | DM |
| `//`, `///` | DM |

## Settings

Reload the extension after changing any settings.

* `auto-comment-blocks-dm.singleLineBlockOnEnter`: If enabled, pressing `Enter` inserts a new commented line at the same indentation, and pressing `Shift+Enter` breaks the comment block.
  + **Caution**: This feature is buggy in many languages (see Issues section), but it seems to work fine for DM.
* `auto-comment-blocks-dm.disabledLanguages`: Add languageIds here to disable any comment completion for that language.
* `auto-comment-blocks-dm.slashStyleBlocks`: Add languageIds here to enable '//' and '///'-style single line comment blocks for that language.

## Issues

* Single-line blocks using `Enter`: if you enable the `singleLineBlockOnEnter` setting, there are a few things to keep in mind:
  + It seems to work fine for DM.
  + For other languages, if you press `Tab` immediately after breaking out of a comment block, it will insert a commented line, for some unknown reason.
* Sometimes multi-line completion/aseterisk insertion doesn't work. The reason is still unknown. It may go away if you reload your workspace.
* Currently, VS Code only allows extensions to overwrite, instead of modify, existing language configurations. This means that this extension may clash with another extension that overwrites the same language configurations, causing one or both not to work. In that case, uninstalling this extension is the only option for now.
