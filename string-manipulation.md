---
title: vc/string-manipulation
description: Modify text in different ways, such as case, word count, and "font"s
published: true
date: 2020-10-20T19:34:02.560Z
tags: 
editor: markdown
---

String manipulation can be done in your channel name template using this format:

`vc/template ""operation:Text to manipulate""`

## Operations:

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
`vc/template ""3w+caps: @@game_name@@""` ⇾ `WORLD OF WARCRAFT`
`vc/template Playing ""acro: @@game_name@@""` ⇾ `Playing WoW`

Multiple operations can be used at once by adding a `+` between them. E.g:
`vc/template ""remshort+3w+acro+caps: It's a small world after all""` ⇾ `ISW`

## "Font"s

There is no way to change the font of any channel name in discord, however there are some font-like mathematical characters in Unicode that we can convert normal characters to. 

Font list:

* `bold` ⇾ 𝐇𝐞𝐥𝐥𝐨 𝐰𝐨𝐫𝐥𝐝!
* `italic` ⇾ 𝐻𝑒𝑙𝑙𝑜 𝑤𝑜𝑟𝑙𝑑!
* `bolditalic` ⇾ 𝑯𝒆𝒍𝒍𝒐 𝒘𝒐𝒓𝒍𝒅!
* `script` ⇾ He𝓁𝓁o 𝓌o𝓇𝓁𝒹!
* `boldscript` ⇾ 𝓗𝓮𝓵𝓵𝓸 𝔀𝓸𝓻𝓵𝓭!
* `fraktur` ⇾ H𝔢𝔩𝔩𝔬 𝔴𝔬𝔯𝔩𝔡!
* `boldfraktur` ⇾ 𝕳𝖊𝖑𝖑𝖔 𝖜𝖔𝖗𝖑𝖉!
* `double` ⇾ H𝕖𝕝𝕝𝕠 𝕨𝕠𝕣𝕝𝕕!
* `sans` ⇾ 𝖧𝖾𝗅𝗅𝗈 𝗐𝗈𝗋𝗅𝖽!
* `boldsans` ⇾ 𝗛𝗲𝗹𝗹𝗼 𝘄𝗼𝗿𝗹𝗱!
* `italicsans` ⇾ 𝘏𝘦𝘭𝘭𝘰 𝘸𝘰𝘳𝘭𝘥!
* `bolditalicsans` ⇾ 𝙃𝙚𝙡𝙡𝙤 𝙬𝙤𝙧𝙡𝙙!
* `mono` ⇾ 𝙷𝚎𝚕𝚕𝚘 𝚠𝚘𝚛𝚕𝚍!
* `scaps` (small caps) ⇾ Hᴇʟʟᴏ ᴡᴏʀʟᴅ!

If you're combining string manipulations (using `+` between them), be sure to add the font last as they don't play nice with the other operations.

Not all characters are supported by most "font"s, such as an `x` in 'scaps', punctuation, or probably most non-ascii letters. In these cases, the original character is displayed.
