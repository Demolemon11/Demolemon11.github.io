## Ongoing tasks:
I'm keep on doing refining the `Settings` page, under `home/spaces_dock.rs`.
I am reloading the `Dock` as ther first thing,
to become one button will enlarge while the other will dislarge Once being clicked
## Difficulties:
However, There is some difficulties, the Dock seems not too easy to adjust,
The button enlarge * dislarge is easy to implmenting via a `static` in `app.rs`

```
pub static APP_PAGE: RwLock<AppPage> = RwLock::new(AppPage::Home);
#[derive(Debug, Clone)]
pub enum AppPage {
    Home,
    Settings,
}
```
And then, there is an home button's example for `static`, settings button is the same way
```
impl Widget for HomeButton {
    fn handle_event(&mut self, cx: &mut Cx, event: &Event, scope: &mut Scope) {
        self.match_event(cx, event);
        self.view.handle_event(cx, event, scope)
    }
    fn draw_walk(&mut self, cx: &mut Cx2d, scope: &mut Scope, walk: Walk) -> DrawStep {
        let nodes = match *APP_PAGE.read().unwrap() {
            AppPage::Home => live!(icon_walk: {width: 50, height: Fit}),
            AppPage::Settings => live!(icon_walk: {width: 30, height: Fit}),
        };

        self.button(id!(home_button)).apply_over(cx, nodes);

        self.view.draw_walk(cx, scope, walk)
    }
}

impl MatchEvent for HomeButton {
    fn handle_actions(&mut self, cx: &mut Cx, actions: &Actions) {
        if self.button(id!(home_button)).clicked(actions) {
            log!("999");
            if let AppPage::Settings = *APP_PAGE.read().unwrap() {
                *APP_PAGE.write().unwrap() = AppPage::Home
            }
            self.view.redraw(cx)
        }
    }
}
```

[**Demo picture here**](https://github.com/Demolemon11/Demolemon11.github.io/blob/hotfix/2024-10-16_18-20-22.png)

## WorkInsights:
VK pair `debug = "full"` is not necessary for me,
it consumes a large amount of disk space while the `log!` is good enough, which just can not be affected, behavir normally.
