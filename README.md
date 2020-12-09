## Overview

Create ANSI art/logos by drawing them in Microsoft Excel. This would make for a fun addition to your cli projects, or a splash screen for a program (provided you know the user's terminal supports truecolor, more on that below).

![Clean Logo](media/clean-logo.png)

## Requirements

Microsoft Excel with macros enabled. This was created using a 2019 version of Excel on Windows, but is likely to work on much older versions as well.

## Code

To view the code press `Alt` and `F11` to open the VBA editor

## Usage

![GUI](media/GUI.png)

1. Ensure macros are enabled
1. Click `Clear All Cells` to clear the workspace
1. Enter the character you would like for an empty non-highlighted cell next to "Blank Char", cell `BG1`
1. Enter the character you would like for an empty highlighted cell next to "Fill Char", cell `AZ1`
1. Draw your logo/spash screen by highlighting cells and typing characters
   * Enter a character into a cell where you would like it to appear. It is recommeneded that each cell contains at most 1 character
   * Highlight cells the color you would like the character in that position to be
1. Set the width and height of the drawing in cells `AL1` and `AS1`
1. Click `Generate Screen` to generate the logo with included ANSI escape characters
1. Click `Copy to clipboard` to copy the generated logo

Cell is highlighted  | Cell has value  | Character and Color Produced
------------------|-------------|-----------------------
No | No | "Blank Char" with default color
No | Yes | Cell value with default color
Yes | No | "Fill Char" with cell highlight color
Yes | Yes | Cell value with cell highlight color

The above drawing produces the following result. Note that the backtick character `` ` `` has been input into "Blank Char" which gives the following 'background'. Using a single space instead would give the cleaner looking background shown above. The cells containing the letters `R`, `G` and `B` are colored to make these characters the corresponding color when printed.

![ANSI Logo](media/Output.png)

The actual escape sequence generated is shown below

<details>

<summary>Full escape sequence</summary>

```
\e[0m```````````````````````````````````````````\n\e[0m``````\e[38;2;0;112;192m###\e[0m``````\e[38;2;255;255;0m####\e[0m````\e[38;2;255;255;0m##\e[0m``\e[38;2;112;173;71m#########\e[0m``\e[38;2;112;48;160m###\e[0m``\n\e[0m``````\e[38;2;0;112;192m###\e[0m``````\e[38;2;255;255;0m####\e[0m````\e[38;2;255;255;0m##\e[0m``\e[38;2;112;173;71m#########\e[0m``\e[38;2;112;48;160m###\e[0m``\n\e[0m``````\e[38;2;0;112;192m###\e[0m``````\e[38;2;255;255;0m####\e[0m````\e[38;2;255;255;0m##\e[0m``\e[38;2;112;173;71m##\e[0m`````````\e[38;2;112;48;160m###\e[0m``\n\e[0m``````\e[38;2;0;112;192m###\e[0m``````\e[38;2;255;255;0m####\e[0m````\e[38;2;255;255;0m##\e[0m``\e[38;2;112;173;71m##\e[0m`````````\e[38;2;112;48;160m###\e[0m``\n\e[0m````\e[38;2;0;112;192m##\e[0m```\e[38;2;0;112;192m##\e[0m````\e[38;2;255;255;0m##\e[0m``\e[38;2;255;255;0m##\e[0m``\e[38;2;255;255;0m##\e[0m``\e[38;2;112;173;71m##\e[0m`````````\e[38;2;112;48;160m###\e[0m``\n\e[0m````\e[38;2;0;112;192m##\e[0m```\e[38;2;0;112;192m##\e[0m````\e[38;2;255;255;0m##\e[0m``\e[38;2;255;255;0m##\e[0m``\e[38;2;255;255;0m##\e[0m``\e[38;2;112;173;71m#########\e[0m``\e[38;2;112;48;160m###\e[0m``\n\e[0m````\e[38;2;0;112;192m##\e[0m```\e[38;2;0;112;192m##\e[0m````\e[38;2;255;255;0m##\e[0m``\e[38;2;255;255;0m##\e[0m``\e[38;2;255;255;0m##\e[0m``\e[38;2;112;173;71m#########\e[0m``\e[38;2;112;48;160m###\e[0m``\n\e[0m````\e[38;2;0;112;192m##\e[0m```\e[38;2;0;112;192m##\e[0m````\e[38;2;255;255;0m##\e[0m``\e[38;2;255;255;0m##\e[0m``\e[38;2;255;255;0m##\e[0m`````````\e[38;2;112;173;71m##\e[0m``\e[38;2;112;48;160m###\e[0m``\n\e[0m``\e[38;2;0;112;192m##\e[0m``\e[38;2;0;112;192m###\e[0m``\e[38;2;0;112;192m##\e[0m``\e[38;2;255;255;0m##\e[0m````\e[38;2;255;255;0m####\e[0m`````````\e[38;2;112;173;71m##\e[0m``\e[38;2;112;48;160m###\e[0m``\n\e[0m``\e[38;2;0;112;192m##\e[0m```````\e[38;2;0;112;192m##\e[0m``\e[38;2;255;255;0m##\e[0m````\e[38;2;255;255;0m####\e[0m`````````\e[38;2;112;173;71m##\e[0m``\e[38;2;112;48;160m###\e[0m``\n\e[0m``\e[38;2;0;112;192m##\e[0m```````\e[38;2;0;112;192m##\e[0m``\e[38;2;255;255;0m##\e[0m````\e[38;2;255;255;0m####\e[0m``\e[38;2;112;173;71m#########\e[0m``\e[38;2;112;48;160m###\e[0m``\n\e[0m``\e[38;2;0;112;192m##\e[0m```````\e[38;2;0;112;192m##\e[0m``\e[38;2;255;255;0m##\e[0m````\e[38;2;255;255;0m####\e[0m``\e[38;2;112;173;71m#########\e[0m``\e[38;2;112;48;160m###\e[0m``\n\e[0m```````````````````````````````````````````\n\e[0m```Logo`Generator`with`\e[38;2;255;0;0mR\e[38;2;0;176;80mG\e[38;2;0;112;192mB\e[0m`color`support```\n\e[0m```````````````````````````````````````````\n

```

</details>

Make sure to output the sequence to a terminal with escape characters enabled, i.e. using `echo -e` in bash instead of just `echo`

## Compatability

This program makes use of 24-bit color ANSI codes to change the output color, which are of the following form

```
\e[38;2;R;G;Bm
```

where `\e` is the escape character and `R`, `G` and `B` are the RGB values from 0 to 255.  

Not all terminals support this format, though many do. [Here](https://gist.github.com/XVilka/8346728) is a list of terminals that do and do not support true color, including how to detect whether the terminal being outputted to supports it.

## Why Excel

The spreadsheet in excel makes for a convenient interface for 'drawing' logos one character at a time, which can then be processed with VBA commands to produce the ANSI sequence.

## Known Issues

Placing `\` in certain positions in the drawing may cause double backslashes to appear in the output, i.e. `\\e[0m` which can lead to undesired behaviour such as the actual escape sequence appearing when outputting to a terminal.
