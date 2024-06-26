# Vim9 Whitespace Highliter

### !!! plugin need vim 9.1 with classes support

This plugin highlite all trailing whitespace characters (see [Supported Whitespace
Characters](#supported-whitespace-characters) below) to be highlighted. Whitespace for the current line will
not be highlighted while in insert mode.

Here is a screenshot of this plugin at work:
![Example Screenshot](https://i.imgur.com/ttfmPXa.png)

## Installation
There are a few ways you can go about installing this plugin:

1.  If you have [Vundle](https://github.com/gmarik/Vundle.vim) you can simply add:
    ```vim
    Plugin 'greeschenko/vim9-whitespace-highliter'
    ```
    to your `.vimrc` file then run:
    ```vim
    :PluginInstall
    ```
2.  If you are using [Pathogen](https://github.com/tpope/vim-pathogen), you can just run the following command:
    ```
    git clone https://github.com/greeschenko/vim9-whitespace-highliter.git ~/.vim/bundle/vim9-whitespace-highliter
    ```
3.  If you are using build in packadd
    ```
    git clone https://github.com/greeschenko/vim9-whitespace-highliter.git ~/.vim/pack/downloads/opt/
    ```
    and add to ~/.vimrc
    ```vim
    packadd vim9-whitespace-highliter
    ```

## Usage
Whitespace highlighting is enabled by default, with a highlight color of red.

Add this code to your ~/.vimrc

```
g:WhitespaceHighliter.Start({
    "guicolor": "gold",
})
```
or
```
g:WhitespaceHighliter.Start({
    "guicolor": "#ff8899",
})
```
or
```
g:WhitespaceHighliter.Start({
    "ctermcolor": "blue",
    "guicolor": "#ff8899",
})
```


## Supported Whitespace Characters
Due to the fact that the built-in whitespace character class for patterns (`\s`)
only matches against tabs and spaces, this plugin defines its own list of
horizontal whitespace characters to match for both highlighting and stripping.

This is list should match against all ASCII and Unicode horizontal whitespace
characters:
```
    U+0009   TAB
    U+0020   SPACE
    U+00A0   NO-BREAK SPACE
    U+1680   OGHAM SPACE MARK
    U+180E   MONGOLIAN VOWEL SEPARATOR
    U+2000   EN QUAD
    U+2001   EM QUAD
    U+2002   EN SPACE
    U+2003   EM SPACE
    U+2004   THREE-PER-EM SPACE
    U+2005   FOUR-PER-EM SPACE
    U+2006   SIX-PER-EM SPACE
    U+2007   FIGURE SPACE
    U+2008   PUNCTUATION SPACE
    U+2009   THIN SPACE
    U+200A   HAIR SPACE
    U+200B   ZERO WIDTH SPACE
    U+202F   NARROW NO-BREAK SPACE
    U+205F   MEDIUM MATHEMATICAL SPACE
    U+3000   IDEOGRAPHIC SPACE
    U+FEFF   ZERO WIDTH NO-BREAK SPACE
```

A file is provided with samples of each of these characters to check the plugin
working with them: whitespace_examples.txt

If you encounter any additional whitespace characters I have missed here,
please submit a pull request.

