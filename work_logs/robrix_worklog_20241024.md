## Today is the happy coders' day (1024)!

## Ongoing tasks:
Keep on doing refining the `Settings` page.
Trying to make some relationship between buttons in dock and the pages:
```
self.ui
    .radio_button_set(ids!(dock_screen.home_tab, dock_screen.settings_tab))
    .selected_to_visible(
        cx,
        &self.ui,
        actions,
        ids!(pages.home_screen, pages.settings_screen),
    );
```
Just fork from moly, only a little difference, Hahhh

## Difficulties:
Can't jump to a new page, the passing of the action is not done properly.
[**A demo picture here**](https://github.com/Demolemon11/Demolemon11.github.io/blob/hotfix/statics/2024-10-24_19-46-15.png)

## WorkInsights:
Thanks to moly that I can code it so fast, Hahhh!
