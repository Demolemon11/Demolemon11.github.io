## Ongoing tasks:
- pr [244](https://github.com/project-robius/robrix/pull/244) => issue [Display verification status as a badge atop the user profile icon](https://github.com/project-robius/robrix/issues/241)
- pr [239](https://github.com/project-robius/robrix/pull/239) => issue [Don't show message text input bar if the user cannot send messages in a room](https://github.com/project-robius/robrix/issues/231)
- pr [248](https://github.com/project-robius/robrix/pull/248) => issue [The status label at the bottom of the RoomsList is not always correct](https://github.com/project-robius/robrix/issues/188)
- pr [246](https://github.com/project-robius/robrix/pull/246) => issue [Properly handle matrix.to links for Rooms](https://github.com/project-robius/robrix/issues/87)

----

[244](https://github.com/project-robius/robrix/pull/244), [239](https://github.com/project-robius/robrix/pull/239) and [248](https://github.com/project-robius/robrix/pull/248) were waiting for review.

But [246](https://github.com/project-robius/robrix/pull/246), might met other bugs, was waiting for reply.
I Have mentioned the truble I met at [here](https://github.com/project-robius/robrix/pull/246).


## Difficulties:
[244](https://github.com/project-robius/robrix/pull/244) Align just don't work, I don't know how to center an `<Icon>` in a `<View>`.

[246](https://github.com/project-robius/robrix/pull/246) The function works only in exceptional circumstances and failure with two panics, all in the pr.

## WorkInsights:
For pr [246](https://github.com/project-robius/robrix/pull/246):

**This will work:**
<video controls>
    <source src="../statics/2024-11-11_14-35-47.webm" type="video/webm">
</video>

----

**This will panic:**
<video controls>
    <source src="../statics/2024-11-11_14-36-27.webm" type="video/webm">
</video>

<style>
  video {
      width: 60%;
      height: auto;
  }
</style>
