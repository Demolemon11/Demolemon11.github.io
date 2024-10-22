[**A demo video here**](https://github.com/Demolemon11/Demolemon11.github.io/blob/hotfix/statics/2024-10-15_19-24-43.webm)

## Ongoing tasks:
I'm keep on doing refining the `Settings` page, under `home/spaces_dock.rs`.

## Difficulties:
I have sovled the problem i mentioned, before this, I newed an issue to ask for solution.
And Alan Poon answered me, there is no in `handle_actions`:
```
self.redraw(&mut cx)
```
The problem was solved finally.


And then, I reloaded `Home` button, btw
```
#[derive(LiveHook, Live, Widget)]
struct Home {
    #[deref]
    view: View,
    #[rust(true)]
    is_open: bool,
}
impl Widget for Home {
    fn handle_event(&mut self, cx: &mut Cx, event: &Event, scope: &mut Scope) {
        self.match_event(cx, event);
        self.view.handle_event(cx, event, scope)
    }
    fn draw_walk(&mut self, cx: &mut Cx2d, scope: &mut Scope, walk: Walk) -> DrawStep {
        let nodes = match self.is_open {
            true => live!(icon_walk: {width: 50, height: Fit}),
            false => live!(icon_walk: {width: 50, height: Fit}),
        };

        self.button(id!(home_button)).apply_over(cx, nodes);

        self.view.draw_walk(cx, scope, walk)
    }
}

impl MatchEvent for Home {
    fn handle_actions(&mut self, cx: &mut Cx, actions: &Actions) {
        if self.button(id!(home_button)).clicked(actions) {
            log!("999");
            self.is_open = !self.is_open
        }
        self.view.redraw(cx)
    }
}

```
'Cause I have learned a lot from `Settings` button, Developing this become much easiser!

## WorkInsights:
Whereas Mr.Julian has shared a breaking debug skill, I immediately apply it in `spaces_dock.rs` of robrix.
However, I found it seems cannot auto apply debug settings for all all descendant components of self-component.
