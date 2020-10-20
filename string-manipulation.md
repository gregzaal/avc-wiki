---
title: vc/string-manipulation
description: Modify text in different ways, such as case, word count, and "font"s
published: true
date: 2020-10-20T14:16:37.465Z
tags: 
editor: markdown
---

String manipulation can be done in your channel name template using this format:

`""operation:Text to manipulate""`

Supported operations are:
* Convert to capital letters:
`""caps: Text""` ⇾ `TEXT`
* Convert to lower case letters:
`""lower: Text""` ⇾ `text`
* Convert to "Title Case":
`""title: text""` ⇾ `Text`
* Swap the upper/lower case:
`""swap: Text""` ⇾ `tEXT`
* Randomize the case (changes hourly):
`""rand: Hmmmmmmm""` ⇾ `hmMmMmMM`
* Convert to acronym (first letter of each word):
`""acro: Text to Manipulate""` ⇾ `TtM`
* Remove short words (a/an/and/at/by/from/in/is/of/on/or/the/to):
`""remshort: Text to Manipulate""` ⇾ `Text Manipulate`
* First word only:
`""1w: Text to Manipulate""` ⇾ `Text`
Also works with `2w` for first two words, or `Nw` where `N` is the number of words.
* Remove unnecessary spaces:
`""spaces:   Text   to   Manipulate ""` ⇾ `Text to Manipulate`
* uwu translator (based on [[1]](https://github.com/QuazzyWazzy/UwU-fy) & [[2]](https://github.com/mackyclemen/uwu-android)):
`""uwu: Surprise!""` ⇾ `Suwpwise!`

## Practical Use

You can use any other template variables inside the text, E.g:
`""3w+caps: @@game_name@@""` ⇾ `WORLD OF WARCRAFT`
`""acro: @@game_name@@""` ⇾ `WoW`

Multiple operations can be used at once by adding a `+` between them. E.g:
`""remshort+3w+acro+caps: It's a small world after all""` ⇾ `ISW`

## "Font"s

There is no way to change the font of any channel name in discord, however we there are some font-like characters in Unicode that we can convert normal characters too. 

If you're combining string manipulations (using `+` between them), be sure to add the font last as they don't play nice with the other operations.

Font list:

* `bold`
* `italic`
* `bolditalic`
* `script`
* `boldscript`
* `fraktur`
* `boldfraktur`
* `double`
* `sans`
* `boldsans`
* `italicsans`
* `bolditalicsans`
* `mono`
* `scaps` (small caps)

In some cases, not all characters are supported by a particular "font", such as an `x` in 'scaps' or probably most non-ascii characters. In these cases, the original character is displayed.
