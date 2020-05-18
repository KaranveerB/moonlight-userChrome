# Moonlight 🌌 userChrome

A dark userstyle for Firefox inspired by [moonlight-vscode-theme](https://github.com/atomiks/moonlight-vscode-theme) and [github-moonlight](https://github.com/Brettm12345/github-moonlight)

![Firefox screenshot with the moonlight theme activated](https://github.com/eduardhojbota/moonlight-userChrome/raw/master/preview.jpg)
Warning: Screenshot does not include modifications made in this fork.

## Fork additions
- [Auto-hiding URL](https://old.reddit.com/r/FirefoxCSS/comments/gc7w2j/collapsing_url_bar_improved_pywal_theme) bar by reddit user [SchokoMilf](https://reddit.com/user/SchokoMilf)
- [Favicon as a close button](https://github.com/MrOtherGuy/firefox-csshacks/blob/master/chrome/combined_favicon_and_tab_close_button.css) by [MrOtherGuy](https://github.com/MrOtherGuy)
- Slight design changes
    - Set tab bar to be on top of navigation bar (default in Firefox)
    - Enabled title bar controls for windows by defaut
    - More subdued design when highlighting menu items
    - Rounded close button when hovering over favicon
    - Padding on left of tab bar
    - Probably other stuff I'm forgetting
- Hacky workarounds
    - Arbitrary border-radius to make something round in `_favicon-close.css`
    - Fixing weird padding in `_tab-bar.css`
    - Code that is probably getting overwritten

## Installation

1. Open your currently active profile folder
    1. In the URL bar type: `about:profiles`
    2. Look for the profile which has the "Default Profile" property set to true
    3. Click on "Open Folder" button belonging to the "Root Directory" property
2. Create a new folder named chrome
3.  - Clone the theme directly into the chrome folder. If you choose this method you will be able to update the theme by pulling the latest files.  
      OR
    - Download and extract the files in the chrome folder
4. If you're running Firefox 69+
    1. In the URL bar type: `about:config`
    2. You will receive a warning to proceed with caution. Accept the Risk and Continue.
    3. In the "Search preference name" input field type `toolkit.legacyUserProfileCustomizations.stylesheets`
    4. Set it to true by double clicking the false value
5. Restart the browser

## Custom styling

The theme comes **as is** but it can be extended using CSS files provided in the custom folder. Further extensions should be included in the same folder to keep the main theme consistent.
To **enable** custom styles, copy and paste the following `@import` statements at the end of the `userChrome.css` file.

### Re-enable title bar controls (MIN-MAX-CLOSE buttons)

For Windows (enabled by default):

```css
@import "custom/_titlebar-controls-enable-windows.css";
```

For macOS:

```css
@import "custom/_titlebar-controls-enable-macos.css";
```

### Disable megabar behavior

```css
@import "custom/_megabar-disable.css";
```

## Disabling fork additions
Certain additions in this fork can be disabled through slight modifiations in the files.

### Disable auto-hiding URL bar
Comment out or delete the following line in `userChrome.css`:
```css
@import '_navigation-bar-hide.css';
```
### Disable favicon as close button
Comment out or delete the following line in `userChrome.css`:
```css
@import '_favicon-close.css';
```

### Remove left padding on tab bar
In `_tab-bar.css` change the 4th values to `0px` for the following lines:

```css
#TabsToolbar {
    padding: 0px 125px 0px 25px !important;
}
```
and
```css
:root[sizemode="maximized"] #TabsToolbar {
    padding: 0px 0px 0px 25px !important;
}
```
## License
NOTE: The `LICENSE` file is the ONLY file that defines the license of this project.
In no way shall this `README.md` file be seen as a legal document that defines
the licensing of this project or have any rights over the contents of the `LICENSE` file.

This project is under a dual license license (GNU-GPLv3 + MIT). Because of this,
please note that both licenses must be included in any redistributions of this project
or parts of this project. The licensing under the GNU-GPLv3 was done to comply with the
terms of the license rather than by personal choice. See the license files for more information.


## Support
There is a fair chance you'll come across bugs or mistakes as I don't know CSS, I haven't read the docs for custom CSS in Firefox, and I haven't read all of the origial code. Because the bugs are
likely my fault, please report them to me rather than upstream and I will try my best to fix them.

### Known Bugs
- Tab bar does not hide when in fullscreen

---
This is the unmodified version of the original developer's support message:
## Support

If you love my work and would like to support my future endeavors I would gladly drink a coffee with you :)

[![Buy me a coffee button](https://github.com/eduardhojbota/moonlight-userChrome/raw/master/buymeacoffee.png)](https://www.buymeacoffee.com/eduardh)
