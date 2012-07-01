---
layout: post
title: "raaarbot for freenode on heroku"
description: "a cheet sheet"
category: programming
tags: [hubot, irc, freenode, bot, server, node, npm, brew, homebrew, heroku, javascript]
---
{% include JB/setup %}

[https://github.com/github/hubot/wiki/Deploying-Hubot-onto-Heroku](https://github.com/github/hubot/wiki/Deploying-Hubot-onto-Heroku)

[https://github.com/nandub/hubot-irc](https://github.com/nandub/hubot-irc)

[https://github.com/github/hubot-scripts](https://github.com/github/hubot-scripts)

[https://grove.io/help/integrations/hubot](https://grove.io/help/integrations/hubot)

And because it's on freenode there's a 5 line flood-kick setting that can't be changed so that's why I've linked to this page.

`* EDIT 2012-07-02` I found a config for [Heroku](http://heroku.com) that fixes the flooding problem. My post on the [fix for Hubot getting flood kicked on Freenode](/hacking/2012/07/02/fix-for-hubot-getting-kicked-from-freenode/)

chat.freenode.net #gyaresu

    help - Displays all of the help commands that raaarbot knows about.
    help <query> - Displays all help commands that match <query>.
    raaarbot <anything related to size, speed, quality, specific body parts> - raaarbot will "that's what she said" that ish
    image me <query>    - The Original. Queries Google Images for <query> and
    knowing is half the battle - display "The Battle" image
    map me <query> - Returns a map view of the area returned by `query`.
    math me <expression> - Calculate the given expression.
    mustache me <url>   - Adds a mustache to the specified URL.
    mustache me <query> - Searches Google Images for the specified query and
    pug bomb N - get N pugs
    pug me - Receive a pug
    script info <script> - Print script help
    script list [-l]     - List all availiable scripts (optional -l for list mode)
    script load <script> - Load a script
    ship it - Display a motivation squirrel
    show storage - Display the contents that are persisted in redis
    show users - Display all users that raaarbot knows about
    sosearch me <query> - Search for the query
    sosearch me <query> with tags <tag list sperated by ,> - Search for the query limit to given tags
    task add <task> - Add a task
    task delete <task number> - Delete a task
    task list tasks - List the tasks
    translate me <phrase> - Searches for a translation for the <phrase> and then
    translate me from <source> into <target> <phrase> - Translates <phrase> from <source> into <target>. Both <source> and <target> are optional
    who is <user> - see what roles a user has
    wiki me <query> - Searches for <query> on Wikipedia.
    xkcd       - The latest XKCD comic
    xkcd <num> - XKCD comic matching the supplied number
    youtube me <query> - Searches YouTube for the query and returns the video

