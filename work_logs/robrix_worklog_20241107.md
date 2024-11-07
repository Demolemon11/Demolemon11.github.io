## Ongoing tasks:
- [pr: 243](https://github.com/project-robius/robrix/pull/243) => [issue: Display verification status as a badge atop the user profile icon](https://github.com/project-robius/robrix/issues/241)
- [pr: 239](https://github.com/project-robius/robrix/pull/239) => [issue: Don't show message text input bar if the user cannot send messages in a room](https://github.com/project-robius/robrix/issues/231)
- [issue: Properly handle matrix.to links for Rooms](https://github.com/project-robius/robrix/issues/87)

## Difficulties:

All in the prs mentioned above.

## WorkInsights:

For [pr: 239](https://github.com/project-robius/robrix/pull/239),
I should not use tokio's runtime in `draw_walk`, it can affect performance a lot, thanks to Mr.Boos & Mr.Zhang.

----

For [pr: 243](https://github.com/project-robius/robrix/pull/243),
What I modified was not Mr.Boos's expectation, but this pr just is a draft so far, I shall modify it later.
What I want to explain is I guess [the func](https://github.com/project-robius/robrix/blob/185459f8cfb6443e38c57149c6d7afd796d770e8/src/verification.rs#L20) is not working properly in [here](https://github.com/project-robius/robrix/blob/185459f8cfb6443e38c57149c6d7afd796d770e8/src/sliding_sync.rs#L972).

[verification status screenshot](../statics/2024-11-07_20-20-08.png)

----

For [issue: Properly handle matrix.to links for Rooms](https://github.com/project-robius/robrix/issues/87),
I met a little trouble in `OwnedRoomId` & `OwnedRoomAliasId` and I am asking for help in the `ruma` official room.
