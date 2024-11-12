## Ongoing tasks:
- pr [244](https://github.com/project-robius/robrix/pull/244) => issue [Display verification status as a badge atop the user profile icon](https://github.com/project-robius/robrix/issues/241)
- pr [239](https://github.com/project-robius/robrix/pull/239) => issue [Don't show message text input bar if the user cannot send messages in a room](https://github.com/project-robius/robrix/issues/231)

These two prs were already finished, but there was some problem with the design pattern and performance, so they were redone.

----


## Difficulties:
For pr [244](https://github.com/project-robius/robrix/pull/244) => issue [Display verification status as a badge atop the user profile icon](https://github.com/project-robius/robrix/issues/241)

There are a large amount of difficulties:
1.The icon's draw will be covered.
solution: restore the verification status to `Profile` struct.

2.The field `verification_state` will be set to its default when robrix's window was resized to mobile layout, not sure if it is a bug or not.

For pr [239](https://github.com/project-robius/robrix/pull/239) => issue [Don't show message text input bar if the user cannot send messages in a room](https://github.com/project-robius/robrix/issues/239)

Waiting for clearer reply.

<video controls>
    <source src="../statics/2024-11-12_19-09-02.webm" type="video/webm">
</video>


## WorkInsights:
When I want to ask some questions, most of the time was wasted, which means I must spend a large amount of time to adjust codes' format to keep neat.

**Thus, I hope to enable formatting and clippy in robrix soon.**

<style>
  video {
      width: 60%;
      height: auto;
  }
</style>
