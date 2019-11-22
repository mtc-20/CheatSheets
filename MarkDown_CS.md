# MarkDown Cheat Sheet
**In random order, some of the cool syntax and some of the useful ones I tend to forget, but use often.**


# Contents
1. [Hyperlinks](#hyperlinks)
   1. [Hyperlinks to headers in another repo](#specific-links)
2. [Section Links](#section-links)
3. [Check Boxes](#check-boxes)
4. [Horizontal Lines](#lines)
5. [Emojis](#emojis)
6. [Tables](#tables)
7. [Block Quotes](#block-quotes)
8. [Hotkeys](#hotkeys)

## Hyperlinks
General rule to create links in MD is to enclose the link text in [ ] followed immdeiately by the link/address inside ( ).
The simplest way to do this would be as follows
```
[link text](web-address)
```
For example, [link to my CheatSheets repo](https://github.com/mtc-20/CheatSheets).


A cleaner way to do this is
```
[link text][intermediate-link-can-even-be-a-number]

#At any location within the document

[intermediate-link-can-even-be-a-number]:web-address
```
For example, here's [another link to my CheatSheets repo][1] , the link is actually located at the bottom of the document, making it cleaner to read.

Alternatively if you dont like numbering links, changing the code to this
```
[link to my MarkDown CheatSheet][md]
```
should still work like so
[link to my MarkDown CheatSheet][md]

### Specific Links
GitHub now has a cool way to even link to specific headers/sections in another repo. Try it out:
[Link to **Saving Files** in my OpenCV CheatSheet][2]
```
[Link text](web-address#header)
```

## Section Links
You can create links to sections/headers within the document itself by enclosing the link text in [ ] followed by the name of the header to be linked in all lowercase
prefixed with a # and enclosed in ( ).
For example, typing this
```
[link text](#header)
```
should give you this [link text](#header) which will take you to the Header section located towards the end of this document.



## Lines
I dont't know if I would really need this but I'm gonna leave it here anyways. This `- - -`, `---`,`***` or `___` ,i.e., atlleast 3 should generate a horizontal line as below
- - - 
**<p align="center">Cool?</p>**
____

## Emojis
Just found this out :sweat_smile: All shortcodes are compiled in this [Emoji Markdown][emd].

So, I'm gonna leave this here:  
:heart: :x: :robot:


For those who don't get it, do check [it out][ldr]

## Block Quotes
Alternative to code blocks, use `>` to get the followinf output
> __<p align="center">Check this out, I'm just writing this so that the line becomes long enough to wrap itself inside the quoteblock, oh and notice how I also got it be bold and centre aligned, maybe I overdid it now? Most of the stuff here, I used to refer to [markdown-here][3]</p>__


## Tables
Tables can be created with the following features:
* header cells which must be separated by atleast 3 dashes `---`
* different alignments for each column can be specified by colons 
* most markdown formating works
* the outer pipes | are not mandatory
```
|  Column1 Label     | Column2 Label| Column3 Label | Column4 Label |
| :---------: |:-----| :--------: |-----: |
| 1           |  This |       This    | This |
| 2           | is       |          is  |  is   |
| 3           |  left      |  ✔    centre   |  right    |
| 4           | aligned      |  ✔   aligned    |  aligned|
| ...           | ...   | ...         | ...    |
| **in bold**  | *in italics*    | 43% ✔       | ` ✔`   |
```
the output for which looks like this


|Column1 Label| Column2 Label| Column3 Label   | Column4 Label |
| :---------: |:-----        | :--------:      |-----:         |
| 1           |This column   |      This column| This column   |
| 2           | is           |          is     |  is           |
| 3           |  left        |       centre    |  right        |
| 4           | aligned      |      aligned    |  aligned      |
| ...         | ...          | ...             | ...           |
| **in bold** | *in italics* |~~strike that ✔~~| `render ✔`    |


## Hotkeys
To show keys(the align tags are optional of course)
```
<p align="center"><kbd>F</kbd> <kbd>U</kbd></p>
```

<p align="center"><kbd>F</kbd> <kbd>U</kbd></p>

so neat, right?


## Check Boxes
Use `[ ]` and `[x]` in your indented list to denote open and closed checkboxes, like so
- [ ] Just remembered I don't really know the syntax to add images or videos
- [ ] ~~Remind self to look into improving readability of MarkDown files~~ *meh*
- [x] Think long and hard about whether you want tables in MarkDown
- [x] Create a repo that consolidates commonly forgotten features




### Header
Just to test the in-document section link

# The End ?
---
___
***
[md]:https://github.com/mtc-20/CheatSheets/blob/master/MarkDown_CS.md
[1]:https://github.com/mtc-20/CheatSheets
[ldr]:https://en.wikipedia.org/wiki/Love,_Death_%26_Robots
[emd]:https://github.com/ikatyang/emoji-cheat-sheet/blob/master/README.md
[3]:https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#tables
[2]:https://github.com/mtc-20/CheatSheets/blob/master/opencv.md#writing-to-file
