[**A demo video here**](https://github.com/Demolemon11/Demolemon11.github.io/blob/hotfix/2024-10-21_20-15-44.webm)

## Ongoing tasks:
I'm keep on doing refining the `Settings` page, under `home/spaces_dock.rs`.
I have finished reloading the `Dock`.
## Difficulties:
In the `match` block, I put `*APP_PAGE.read().unwrap()` outside while `*APP_PAGE.write().unwrap` inside, which is a deadlock.
Fianlly, I put the `*APP_PAGE.write().unwrap` outside the `match` block, and it works.



## WorkInsights:
VK pair `debug = "full"` is not necessary for me,
it consumes a large amount of disk space while the `log!` is good enough, which just can not be affected, behavir normally.
