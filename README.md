# some-sidebery-tweaks
**Tested on Firefox 111.0 (64-bit, Windows 11)**

Originally Created: 03/13/2021 Edited: 3/18/2023

• [Sidebery beta v5](https://github.com/mbnuqw/sidebery/releases) (**5.0.0b31**)

> [!IMPORTANT]
> Hello to anyone who reads this, for the forseeable future this repo _is no longer being maintained_.

<details>
<summary>
A more long winded explanation here:
</summary>
I'm leaving everything just how it was (I don't really know the right etiquette for this) but I don't I have the capacity anymore to keep this up to date. I seem to be using Sidebery (v5.0.0rc4) at the time of writing this (9/7/23) and I have had no issues with dragging tabs around or my bookmarks bar clipping into the sidebar. 
	Anyone is, of course, free to fork this repo and modify and answer and open issues as much as they'd like. Thank you for your time
- redundakat
</details>

`menuShow`, `sideberyMods`, `darkContextMenu`, and `sideberyTweaks`
were either created by me or heavily modified by me
everything else is stolen from [MrOtherGuy](https://github.com/MrOtherGuy/firefox-csshacks).

Huge thanks to my friend nearcatch for helping me debug and for giving me the original code for sideberyMods.

• [Reddit Post](https://www.reddit.com/r/FirefoxCSS/comments/z8k0a5/a_few_sidebery_and_firefox_tweaks_v20_2_years/)

• [Adaptive Tab Bar Color](https://addons.mozilla.org/en-US/firefox/addon/adaptive-tab-bar-color/) for matching sidebery's color with the tab's color


https://user-images.githubusercontent.com/38409600/204728178-7745f2c9-e6e2-4917-8de6-648609f0746d.mp4

## Colored Tabs Setup
<details>
<summary>Instructions for coloring tabs on hover</summary>

Once you have your userChrome.css file set up following [these](https://www.reddit.com/r/FirefoxCSS/comments/73dvty/tutorial_how_to_create_and_livedebug_userchromecss/) instructions, (and you have sidebery installed) follow these steps: 

1) Paste the code from sideberyTweaks.txt into the native custom css editor. (or use sideberyTweaksv5 if you've updated to the newer version of sidebery)
	* Configure panel → Styles editor → Sidebar 
	* If you did this correctly you can now edit the colors of your tabs depending on if you're hovering over them.

Changing the links will allow you to customize what tabs you want colored.

```css
.Tab[title*="https://github.com"], .PinnedTab[title*="https://github.com"] {
	--tabs-bg-hover: var(--white); /* default hover background */
	--tabs-bg-active: var(--white); /* default mouse-pressed background */
	--tabs-activated-bg: var(--white); /* default current background */
}
```

In the betav5 the variables have changed, use this template instead:
```css
.Tab[title*="https://github.com"], 
.PinnedTab[title*="https://github.com"] {
	--tabs-activated-bg: var(--white); /* default current background */
	--frame-el-overlay-hover-bg: var(--white); /* hover bg */
}
```
I hope they revert this change as this seems so much more clunky :/
But it appears that `--hover-bg` and `--clicked-bg` no longer exist 

2) Copy the userChrome.css from here into your userChrome.css you set up, and paste the hacks folder into your chrome folder.
3) If you're interested in the "Open in New Private Tab" option, check out this [github](https://github.com/xiaoxiaoflood/firefox-scripts) for instructions.
</details>

## Auto Hiding Sidebar
<details open>
<summary>Instructions on the autohiding sidebar files</summary>

There are three sideberyMod files, I will try to explain why they're different and why you might want to use them. All three are interchangable, you only need one to maintain the auto-hiding functionality of the mod. 
File | Side | Explanation | Video Link
--- | --- | --- | ---
[*sideberyMods.css*](https://github.com/Redundakitties/colorful-minimalist/blob/main/hacks/sideberyMods.css) | Right |• Covers window-content when hovered <br>• Hides by changing width of panel | <img src="https://user-images.githubusercontent.com/38409600/234763194-a3fcedc6-5c8c-466a-b7ad-41afb1aa72c9.gif" align="center" width="120">
[*sideberyModsLEFT.css*](https://github.com/Redundakitties/colorful-minimalist/blob/main/hacks/sideberyModsLEFT.css) | Left |• By default covers window content when hovered <br>• Hides by changing width of panel <br>• If you uncomment `.ScrollBox:not(:hover) {--tabs-indent: 0px;}` in sideberyTweaksv5.txt you get this effect| <img src="https://user-images.githubusercontent.com/38409600/235023717-e0c6d5ba-fb6f-4053-9811-47449cfe7376.gif" alt="demo" align="center" width="120"> 
[*sideberyModsLeftSlide.css*](https://github.com/Redundakitties/colorful-minimalist/blob/main/hacks/sideberyModsLeftSlide.css) | Left |• Covers window content on hover <br>• Hides by sliding back and forth<br>• Make sure to change pinned tabs to globally-right in sidebery settings | <img src="https://user-images.githubusercontent.com/38409600/234763781-1e36691d-ec58-440d-9e9a-60fce33b091c.gif" align="center" width="120"> 

Code relating to autohiding the sidebar can be found in [hacks/sideberyMods.css](https://github.com/Redundakitties/colorful-minimalist/blob/main/hacks/sideberyMods.css). The specific variables you should tinker with are these: 
```css
:root {
    --autohide-sidebar-extended: 230px; /* width of each tab when shown */
    --autohide-sidebar-collapsed: 34px; /* width of each tab when hidden */
    --sidebar-height: 100vh;
}
```
</details>

## Changelog
<details>
<!-- Necessary blank line -->
<summary> 9/7 No longer maintaining repo for the forseeable future :/ (I just don't have the free time I once had anymore) 
</summary>

+ 4/27 Added ability show indented tabs on hover <a href="https://user-images.githubusercontent.com/38409600/235023717-e0c6d5ba-fb6f-4053-9811-47449cfe7376.gif">demo</a>
+ 4/1 Fixed colored tabs setup instructions
+ 3/18 updated out of date parts of my readme (updated for b31), created some code to handle if the sidebar-header is shown (see issue https://github.com/Redundakitties/colorful-minimalist/issues/4) 
+ 2/1 - updated sidebery to b30
+ 12/21 - removed tabsintitlebar selector because it's not necessary and was breaking the css for machines where tabsintitlebar=false. 
+ 12/2 - added `sideberyModsLeftSlide.css`
+ 11/30 - added `sideberyModsLEFT.css`
+ 11/28/2022
	- fixed autohide because it broke
	- removed weird purple top left square from menuShow.css
	- updated sidebery to beta v5 (highly recommend)
		- due to updating sidebery, had to change a bunch of sideberyTweaks.txt
		- made a new file for this called sideberyTweaksv5.txt
	- removed [custom_menupopup_check_icons.css](https://github.com/MrOtherGuy/firefox-csshacks/tree/master/chrome/custom_menupopup_check_icons.css)
</details>
