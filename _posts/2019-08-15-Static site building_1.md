---
layout: post
title: Static site building_1
date: 2019-08-15 15:49:00
desc: First post about the building of static site.
---

In this post i try to explain all the issues and solution which are faced also overcomed by me. I hope it might help someone who face the same kind of situation. I think it might help me in future   

Github pages are powered by jekyll on the backend  
Github pages also work well on html pages, jekyll treats files without front matter as static assets  
Git - Version control system  
Github - Webhosting service that uses Git  
Jekyll - powerful static site generator. It is based on templates(layouts in jekyll) it reduces the same markup used on every pages. We can create a layout and it get used in all pages.  

> {{ content }}  
This is called liquid tags     


Why jekyll was called static site generator?  
static site generators actually collects list of files and build them as a site.  
Dynamic site generators(like wordpress, drupal) are works by   
1. User request the webpage  
2. Then request reached the werbserver  
3. Webserver contacts wordpress  
4. wordpress then collects data from database.  

Static site generators works in same like as Dynamic CMS but in the phase of 3 and 4 it only contains the files.  
1. User request the webpage    
2. Then request reaches the webserver  
3. Webserver fetches the jekyll files  


Why i use static site generator?  
Jekyll is meant for its less complexity nature. It is a static site with an liquid tags.  
To make a static site it enough to know about html, js, css  
In case of building a dynamic site an developer should know about html,css,js also he must have knowledge about php, mysql, wordpress structure.  

Static site speed is large than dynamic site  

Security risk in static site is very much less when compared with the dynamic sites.  

Servers which host static sites can serve large amount of traffic while the servers which host dynamic sites will contain a databse on the backend. Hence ther is a possibility that server will overload with more traffic.  

Jekyll is worked on git in this it is possible to move back to the old version using the version control system. Also we can have a separate branch to work separately.  

```
---
layout: default
title: Hank Quinlan, Horrible Cop
---
```

Above mentioned is called Front-matter and it is placed at top of the file. Jekyll will process this content at first and fetch the necessary layout for the page.  

Every time you commit a file that specifies layout: default at the top, Jekyll will magically generate the full HTML document by replacing {{ content }} in _layouts/default.html with the contents of the committed file.  
