# MarkDown Cheat Sheet
**In  random order**


# Contents
1. [Hyperlinks](#hyperlinks)
2. [Section Links](#section-links)
3. [Check Boxes](#check-boxes)


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

Alternatively if you dont like numbering links, this also works 
```
[link to my MarkDown CheatSheet][md]
```

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


## Check Boxes
Use [ ] and [x] in your indented list to denote open and closed checkboxes, like so
- [ ] Remind self to look into improving readability of MarkDown files
- [x] Create a repo that consolidates commonly forgotten features




### Header
Just to test the in-document section link

# The End ?
[md]:https://github.com/mtc-20/CheatSheets/blob/master/MarkDown_CS.md
[1]:https://github.com/mtc-20/CheatSheets
