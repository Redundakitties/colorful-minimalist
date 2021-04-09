# colorful-minimalist
**Tested on Firefox 87.0 (64-bit, Windows 10)**

Colorful Sidebery tabs with minimalist buttons taken from [here](https://github.com/MrOtherGuy/firefox-csshacks)

Preview: 
https://user-images.githubusercontent.com/38409600/114223136-74689d80-993d-11eb-9558-268678e16ade.mp4


Setup
======
Once you have your userChrome.css file set up following [these](https://www.reddit.com/r/FirefoxCSS/comments/73dvty/tutorial_how_to_create_and_livedebug_userchromecss/) instructions, (and you have sideberry installed) follow these steps: 

1) Paste the code from sideberyTweaks.txt into the native custom css editor. 
  * Configure panel -> Styles editor -> Sidebar 
  * If you did this correctly you can now edit the colors of your tabs depending on if you're hovering over them.

Changing the links will allow you to customize what tabs you want colored.

```
.Tab[title*="https://github.com"], .PinnedTab[title*="https://github.com"] {
	--tabs-bg-hover: var(--white); /* default hover background */
	--tabs-bg-active: var(--white); /* default mouse-pressed background */
	--tabs-activated-bg: var(--white); /* default current background */
}
```

2) Copy the userChrome.css from here into your userChrome.css you set up, and paste the hacks folder into your chrome folder.

Contact
====
If you have any questions don't hesitate to ping me my discord is GracefulLion#9559
