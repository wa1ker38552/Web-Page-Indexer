# Web-Page-Indexer

This program starts off with ```https://google.com``` and indexes all links found on the inital website and adding it to a text file. It then indexes the next link on the text file and adds all those links to the text file as well, repeating this forever.

The program only writes down new domains, IE: ```https://google.com/account/about``` will not be logged down if ```https://google.com``` has already been logged down.
The program also ignores certificate validation if it's given an SSL certificate error.

Occasionally, the program will just stop for a long time while indexing a website, if that happens, just change the number on ```i.txt``` by one to skip the current domain.

**Files**

```i.txt``` saves the last website indexed by the bot. <br/>
```index.txt``` is a list of all websites found by the bot.
