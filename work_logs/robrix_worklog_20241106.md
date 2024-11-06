## Ongoing tasks:
- [Apply a yellow background highlight to messages that mention the current user](https://github.com/project-robius/robrix/issues/229)

## Difficulties:
[Add the code here](https://github.com/project-robius/robrix/blob/185459f8cfb6443e38c57149c6d7afd796d770e8/src/home/room_screen.rs#L2425)
```
if let Some(mentions) = message.mentions() {
        let client = get_client().unwrap();
        let self_id = client.user_id().unwrap();
        if mentions.user_ids.iter().any(|x|x == self_id) {
            let color = vec3(0.9, 0.9, 0.1);
            item.apply_over(cx, live!(
                draw_bg: {
                    color: (color)
                }
            ));
            item.redraw(cx);
        log!("{} mentioned me!", event_tl_item.sender())
        }
    }
```
These possess two functionality:
- If self `UserId` was mentioned, `apply_over` this message's bg to yellow.
- Log the sender's `UserId` of this message.

----

[Add the code here](https://github.com/project-robius/robrix/blob/185459f8cfb6443e38c57149c6d7afd796d770e8/src/home/room_screen.rs#L309-L323)
```
// fn pixel(self) -> vec4 {
//     return mix(
//         mix(
//             #ffffff,
//             #fafafa,
//             self.hover
//         ),
//         #c5d6fa, // light blue
//         self.highlight
//     )
// }
color: #F9F9F9
```
Replace func `pixel` with a fixed color `#F9F9F9`.
If you do not comment out func `pixel`, func `apply_over` will not work.

----
Upon completion of the above two changes, run robrix, then you will find out not all the message that mentioned yourself is yellow.
I have debugged this all day, and don't why this is.

## WorkInsights:
Some pictures for message of mentioned self highlight, it's random, IMHO:

[Mr.Boos: off](../statics/2024-11-06_17-13-19.png)

[Jianfeng Luo: on](../statics/2024-11-06_17-13-32.png)

[Person A: on](../statics/2024-11-06_17-14-01.png)

[Person B: off](../statics/2024-11-06_17-14-51.png)

[Person C: on](../statics/2024-11-06_17-20-47.png)
