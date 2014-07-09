---
layout: post
title: "Outsource this"
description: ""
category: hacking 
tags: [hacking, regex, bash, sed, coreutils, linux, utf8, latin1, unicode, gcat, gsed]
---
{% include JB/setup %}

90 Thousand line broken CSV file. UTF-8. 

Cyrilic and hanzi characters/logograms showing...

... Latin-1 diacritic characters broken.

i.e. `FlÃ³rez` instead of `Flórez`

    Attached is a zip file containing two text files.

    I’ve removed most character-type garbage and (non-visible) termination characters. 

    I wouldn’t use it to import into a database but this should be adequate for your stated requirements. 

    Should you wish any further alterations please don’t hesitate to ask.

*Final command used to clean, sort, remove duplicates, reshuffle and output to separate file*:

```bash
⇒  gsed -e 's/[0-9]//g' -e 's/,/ /g' -e 's/Ã©/é/g' -e 's/"//g' -e '/^$/d' -e 's/Â´/´/g' -e 's/Ãº/ú/g' -e 's/Ã±/ñ/g' -e 's/Ã³/ó/g' -e 's/Ã¡/á/g' -e 's/Ã¹/ù/g' -e 's/Ã /Á/g' -e 's/Ã‘/Ñ/g' -e 's/  / /g' -e 's/[[:space:]]$//' -e 's/Ã²/ò/g' -e 's/Ã­/í/g' -e 's/Ã¬/ì/g' -e 's/Ã¼/ü/g' -e 's/Ã€/À/g' -e 's/Ã§/ç/g' -e 's/Ã¨/è/g' -e 's/Ã‰/É/g' -e 's/Ã“/Ó/g' -e 's/Ãª/ê/g' -e 's/Ã¤/ä/g' -e 's/ÃŠ/Ê/g' -e 's/Ã¶/ö/g' -e 's/Ãš/Ú/g' -e 's/Ã^Í/Í/g' -e 's/Ã^Á/Á/g' -e 's/ÃŒ/Ì/g' -e 's/Ã®/î/g' -e 's/Ã¯/ï/g' -e 's/Ã£/ã/g' -e 's/Ã„/Ä/g' -e 's/Ã/à/g' 90K_list_of_names.csv |sort |uniq | gshuf > 80K_clean_list.txt
```

*Followed by a command to remove the newline (carriage return) characters and replace them with two spaces for design use*:

```bash
⇒  gsed ':a;N;$!ba;s/\n/  /g' 80K_clean_list.txt > two_space_separated.txt
```

*Show file with line breaks, tabs and non-printing characters*

`gcat -A thing.txt`

Great reference: [UTF-8 Encoding Debugging Chart](http://www.i18nqa.com/debug/utf8-debug.html)
