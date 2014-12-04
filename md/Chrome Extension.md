# Chrome Extension

Browser extensions are small but a fun and powerful tool to play with.

[Official documentation](https://developer.chrome.com/extensions/overview)

**What’s cool for us?**

One of the most interesting points to us is you can inject Javascript to any webpages you are viewing. It means you can turn every webpages into your playground. You can get a feeling of hacking (It all happens just on your browser, so it actually doesn’t affect to original website).

It’s similar to “bookmarklets” like [kikkass](http://kickassapp.com/) in some points.

**Some cool browser extensions**

*   [“Add Art”](http://add-art.org/) (firefox addons)

*   It replaces all ad on the page with art.

*   [“The world without colors”](https://chrome.google.com/webstore/detail/%E8%89%B2%E3%81%AE%E3%81%AA%E3%81%84%E4%B8%96%E7%95%8C/fjehhencmaeeccodlgnhgacgfbajhijb?hl=ja)

*   It takes all colors off from internet.

*   [“Don’t Care Button”](https://chrome.google.com/webstore/detail/%E3%81%A9%E3%81%86%E3%81%A7%E3%82%82%E3%81%84%E3%81%84%E3%81%AD%EF%BC%81/jbaaibcamkmgakjkcedlkdnggnapmoaa?hl=ja)

*   It pushes ALL Like buttons on the page instead of you

(Feel free to add anything if you know)

---

**Quick start overview**

1.  Make a folder and put HTML/CSS/JS files with “manifest.json”
2.  Load the folder from Google Chrome’s [extensions page](chrome://extensions/)
3.  Ready to go

---

**Example projects**

[](https://github.com/yukiy/chrome-extensions)[https://github.com/yukiy/chrome-extensions](https://github.com/yukiy/chrome-extensions)

*   Replace all images and texts
*   Make tabs a piano

--- 

**How to install**

You can just put all files in a folder and load from  [](chrome://extensions/)[chrome://extensions/](chrome://extensions/).

Turn on “Developer mode” at the right top and “Load unpacked extension…”, then choose the folder.

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Gde1YxGb4kp_p.257357_1416874739341_Screen%20Shot%202014-11-24%20at%2019.17.38.png)

---

**Basic files inside a folder**

*   **manifest.json** 

*   This is the setting file for name, version, browser/page actions, icon’s URL, permission, etc. [details](https://developer.chrome.com/extensions/manifest)

*   **icon.png**

*   16x16, 48x48 and 128x128 png file. [details](https://developer.chrome.com/apps/manifest/icons)

*   **background.html**

*   This is invisible HTML working in background. You can choose it runs all time ([background pages](https://developer.chrome.com/extensions/background_pages)) or runs only when needed ([event pages](https://developer.chrome.com/extensions/event_pages)).

*   **popup.html**

*   This is small HTML pop up window when you click the icon (if needed).

*   **and any other files needed**

---

**Type**

First, you can choose what type is suitable for your extension’s function.

**[Browser Actions](https://developer.chrome.com/extensions/browserAction)**

: The extension is suitable for most web pages.

: The icon is displayed at the right top of a browser

**[Page Actions](https://developer.chrome.com/extensions/pageAction)**

: The extension is suitable for a (few) specific web page(s).

: The icon is displayed inside URL bar

What you can do is not so different between these two types. It’s mainly for your browser’s top bar keep organized (it’s not make sense if there are always icons for only working with a specific page).