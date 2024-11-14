## Ongoing tasks:
- issue [Display verification status as a badge atop the user profile icon](https://github.com/project-robius/robrix/issues/241)
- issue [Investigate using GenUI's GRouter component for better navigation between multiple app screens](https://github.com/project-robius/robrix/issues/242)

## Difficulties:
For issue [Display verification status as a badge atop the user profile icon](https://github.com/project-robius/robrix/issues/241)

It still could not work..., waiting for Julian's reply.

----

For issue [Investigate using GenUI's GRouter component for better navigation between multiple app screens](https://github.com/project-robius/robrix/issues/242)

GRouter is a new framework, docs is rare.

It has no register on `crate.io` & `docs.rs` yet, so I clone the repo but there are some errors.

There are a large difficulties that need to ask for help.

## WorkInsights:
When I want to ask some questions, most of the time was wasted, which means I must spend a large amount of time to adjust codes' format to keep it neat.

**Thus, I hope to enable formatting and clippy in robrix soon.**


Robrix message ontology is divided into two types, just `plaintext_view` and `html_view`:
```
HtmlOrPlaintext = {{HtmlOrPlaintext}} {
    width: Fill, height: Fit, // see above comment
    flow: Overlay

    plaintext_view = <View> {
        visible: true,
        width: Fill, height: Fit, // see above comment
        pt_label = <Label> {
            width: Fill, height: Fit, // see above comment
            draw_text: {
                wrap: Word,
                color: (MESSAGE_TEXT_COLOR),
                text_style: <MESSAGE_TEXT_STYLE> { font_size: (MESSAGE_FONT_SIZE) },
            }
            text: "[plaintext message placeholder]",
        }
    }

    html_view = <View> {
        visible: false,
        width: Fill, height: Fit, // see above comment
        html = <RobrixHtml> {}
    }
}
```

Essentially, `plaintext_view` <=> `<label>`, `html_view` <=> `<Html>`.

Issue84, 87 and 222, for which the first thing to do is to draw `message tag`, `user tag`, `room tag`.

Once User sends a message containing a http or https link, that is `<Html>`. instead of `<Label>`, and the link is in the `<a></a>` in the real html

It is easy to get the label and determine if it is `matrix.to` while hard to find out the rendering logic that link to tag.

<style>
  video {
      width: 60%;
      height: auto;
  }
</style>
