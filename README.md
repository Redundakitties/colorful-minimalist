# some-sidebery-tweaks
**Tested on Firefox 107.0 (64-bit, Windows 11)**

Originally Created: 03/13/2021 Edited: 11/28/2022 

Colorful Sidebery tabs created by me and minimalist buttons taken from [here](https://github.com/MrOtherGuy/firefox-csshacks)

[Preview](https://imgur.com/a/s1wzdQZ)

[Reddit Post](https://www.reddit.com/r/FirefoxCSS/comments/m4cqse/a_few_sidebery_and_firefox_tweaks/)

# Setup

Once you have your userChrome.css file set up following [these](https://www.reddit.com/r/FirefoxCSS/comments/73dvty/tutorial_how_to_create_and_livedebug_userchromecss/) instructions, (and you have sideberry installed) follow these steps: 

1) Paste the code from sideberyTweaks.txt into the native custom css editor. (or use sideberyTweaksv5 if you've updated to the newer version of sidebery)
	* Configure panel → Styles editor → Sidebar 
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
3) If you're interested in the "Open in New Private Tab" option, check out this [github](https://github.com/xiaoxiaoflood/firefox-scripts) for instructions.


## Changelog

11/28/2022
- fixed autohide because it broke
- removed weird purple top left square from menuShow.css
- updated sidebery to beta v5 (highly recommend)
	- due to updating sidebery, had to change a bunch of sideberyTweaks.txt
	- made a new file for this called sideberyTweaksv5.txt

## Contact

If you have any questions don't hesitate to ping me my discord is GracefulLion#9559
