---
layout: post
title: "Apache, MySQL and PHP on OS X 10.8 Mountain Lion"
description: ""
category: hacking
tags: [10.8, mountainlion, apple, osx, apache, php, mysql, server, sysadmin]
---
{% include JB/setup %}

Following this guide: [http://coolestguyplanettech.com/downtown/install-and-configure-apache-mysql-php-and-phpmyadmin-osx-108-mountain-lion](http://coolestguyplanettech.com/downtown/install-and-configure-apache-mysql-php-and-phpmyadmin-osx-108-mountain-lion)

I did indeed install the package from the MySQL site.

I wanted to leave my project folders where they live normally in `~/programming/projects/` which meant I had to enable:

    Include /private/etc/apache2/extra/httpd-userdir.conf

in `/etc/apache2/httpd.conf` and create the file `/etc/apache2/users/gyaresu.conf` to which I added:

    <Directory "/Users/gyaresu/programming/projects/">
    Options Indexes MultiViews
    AllowOverride All
    Order allow,deny
    Allow from all
    </Directory>

Of course I want multiple websites which of course means Name Based Virtual Hosts so I just added some entries to `/etc/apache2/extra/httpd-vhosts.conf` like:

    <VirtualHost *:80>
        DocumentRoot "/Users/gyaresu/programming/projects/phpmyadmin"
        ServerName "phpmyadmin"
    </VirtualHost>
    
    <VirtualHost *:80>
        DocumentRoot "/Users/gyaresu/programming/projects/workthing"
        ServerName "workthing"
    </VirtualHost>

Now of course I've got to edit the `/etc/hosts` file so my computer knows to look locally:

    127.0.0.1   workthing
    127.0.0.1   phpmyadmin

You'll notice phpmyadmin there. That's just a matter of downloading the package and running the setup as instructed in the linked post.

Now I haven't looked into fixing the next issue I found but I'll update this later when I look into it.

Getting the `.htaccess` commands to work required an addition to `/etc/apache2/httpd.conf`:

    <Directory "/Users/gyaresu/programming/projects/workthing/">
        Options Indexes FollowSymLinks MultiViews
        AllowOverride All
    </Directory>

Of course I don't want to have to add that for every project so we'll whether it annoys me enough to solve.

So that wasn't terribly hard at all. Great post from [coolestguyplanettech.com](coolestguyplanettech.com).
