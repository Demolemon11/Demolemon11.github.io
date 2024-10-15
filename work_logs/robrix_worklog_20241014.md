---
layout: default
---

## Ongoing tasks:
In the meantime I'm going to refine the `Settings` page, under `home/spaces_dock.rs`.

## Difficulties:
The first thing to do is: after the user clicks on the Settings gear, the gear should re-render the button (I re-apply_over it to 50, it was 25), but unfortunately, it doesn't render correctly, so I'll try to make sure that it does.
I overloaded `Settings`
```
    Settings = {{Settings}} {
        <View> {
            width: Fit, height: Fit
            // FIXME: the extra padding on the right is becase the icon is not correctly centered
            // within its parent
            padding: {top: 8, left: 8, right: 12, bottom: 8}
            align: {x: 0.5, y: 0.5}

            settings_button = <SettingsButton> {}
        }
    }
```
`SettingsButton` from:
```
    SettingsButton = <Button> {
        enabled: true
        draw_bg: {
            fn pixel(self) -> vec4 {
                let sdf = Sdf2d::viewport(self.pos * self.rect_size);
                return sdf.result
            }
        }
        draw_icon: {
            svg_file: (ICON_SETTINGS),
            fn get_color(self) -> vec4 {
                return (COLOR_TEXT_IDLE);
                // return #x566287; // grayed-out #1C274C until enabled
            }
        }
        icon_walk: {width: 25, height: Fit}
    }
```
The `width` inside `icon_walk: {width: 25, height: Fit}` mentioned above is `25` , I reloaded it in `draw_walk` as `50` when button is clicked,
```
    fn draw_walk(&mut self, cx: &mut Cx2d, scope: &mut Scope, walk: Walk) -> DrawStep {
        if self.is_open {
        log!("666");
            self.button(id!(settings_button)).apply_over(
                cx,
                live! (
                    icon_walk: {width: 50, height: Fit}
                ),
            )
        }
        self.view.draw_walk(cx, scope, walk)
    }
```
```
impl MatchEvent for Settings {
    fn handle_actions(&mut self, cx: &mut Cx, actions: &Actions) {
        if self.button(id!(settings_button)).clicked(actions) {
            log!("Settings button clicked");
            self.is_open = !self.is_open
        }
    }
}

```
But it doesn't work properly, it will jerk (clicking many times may only work once or twice, i.e., successfully print "666"), the relevant code I and 郭柯震 together to study a bit.

But there was no way for me to solve it, I suspect it is a bug with makepad on linux.

I watched the salon that Mr. Zhang shared on Saturday, and Mr. Zhang's collapsible title bar performs well, But it doesn't seem to work properly on Linux.

I shall report this as an `issue` to makepad soonly.

[Here is a demo video](https://github.com/Demolemon11/Demolemon11.github.io/blob/hotfix/statics/2024-10-14_21-29-59.webm)

## WorkInsights:
None
