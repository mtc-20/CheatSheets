# MarkDown Cheat Sheet
**In random order, some of the cool syntax and some of the useful ones I tend to forget, but use often.**


# Contents
1. [Hyperlinks](#hyperlinks)
2. [Section Links](#section-links)
3. [Check Boxes](#check-boxes)
4. [Horizontal Lines](#lines)
5. [Emojis](#emojis)

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
For example, here [another link to my CheatSheets repo][1] , the link is actually located at the bottom of the document, making it cleaner to read.

Alternatively if you dont like numbering links, changing the code to this
```
[link to my MarkDown CheatSheet][md]
```
should still work like so
[link to my MarkDown CheatSheet][md]



## Section Links
You can create links to sections/headers within the document itself by enclosing the link text in [ ] followed by the name of the header to be linked in all lowercase
prefixed with a # and enclosed in ( ).
For example, typing this
```
[link text](#header)
```
should give you this

[link text](#header)

## Lines
I dont't know if I would really need this but I'm gonna leave it here anyways. This `- - -` should generate a horizontal line as below
- - - 
**<p align="center">Cool?</p>**
- - - 

## Emojis
Just found this out :sweat_smile: All shortcodes are compiled in this [Emoji Markdown][emd].

So, I'm gonna leave this here:  
:heart: :x: :robot:


For those who don't get it, do check [it out][ldr]


## Check Boxes
Use `[ ]` and `[x]` in your indented list to denote open and closed checkboxes, like so
- [ ] Just remembered I don't really know the syntax to add images
- [ ] Remind self to look into improving readability of MarkDown files
- [ ] Think long and hard about whether you want tables in MarkDown
- [x] Create a repo that consolidates commonly forgotten features




### Header
Just to test the in-document section link

# The End ?
[md]:https://github.com/mtc-20/CheatSheets/blob/master/MarkDown_CS.md
[1]:https://github.com/mtc-20/CheatSheets
[ldr]:https://en.wikipedia.org/wiki/Love,_Death_%26_Robots
[emd]:https://github.com/ikatyang/emoji-cheat-sheet/blob/master/README.md
