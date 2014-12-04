# Agregating Hackpad Content

this is a hackpad for figuring out how to agregate content fron the notes in hackpad and create a frontend interface (or push to a tumblr) that could be more presentable for the general public.

Also, if there were a Twitter hook that tweeted changes from a robot-account, I'd totally use it for some of my other projects. Github has a similar functionality that works great with Jekyll sites. Set it up for [Cooper Art Student Council](https://twitter.com/cooperasc) to let people subscribe to changes.

(also, I'd be curious about how we can archive, in case hackpad gets bought and shut down / EOLd like etherpad: [](https://blog.brainsik.net/2009/etherpad-to-shut-down-after-google-acquisition))https://blog.brainsik.net/2009/etherpad-to-shut-down-after-google-acquisition)  specifically, tools for scraping and downloading raw data.

Site admins can do periodic dumps in various formats from the [import/export page](https://sfpc.hackpad.com/ep/admin/import-export), and every user can export their own pages from their [profile page](https://sfpc.hackpad.com/ep/profile/). You all can also, from there, authorize background-syncing every change to followed pads with your Dropbox.

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_hGbsIqHjiZu_p.77233_1381181513750_Screen Shot 2013-10-07 at 5.30.36 PM.png)

Just did Hackpad exports in HTML and Markdown and they're totally usable, but don't backup images locally. Maybe this is something you could figure out [Moises](/ep/profile/v6pSS8EP8fM)? Sucks to lose all the visuals if everything goes under.

**TECHNOLOGIES NEEDED**

*   npm hackpad
*   node
*   backbone?
*   isotope
*   tumblr API