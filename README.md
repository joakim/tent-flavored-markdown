# Tent Flavored Markdown

This is a work-in-progress suggestion for a standard Tent flavor of Markdown. It builds on the existing [TFM](https://tent.io/docs/post-types#markdown) of Status, adding features suitable for longer texts. The existing TFM syntax remains as a [limited subset](#limited-subset) for short texts.

## Inline Mention

`^[name](0)` is the syntax used to reference an entity. `name` is the display
text and `0` is the index of the mention in the `mentions` array.

```json
{
  // ...
  "mentions": [
    {
      "entity": "https://jesse.tent.is"
    },
    {
      "entity": "https://daniel.tent.is"
    }
  ],
  "content": {
    "text": "Hey ^[Jesse](0) and ^[Daniel](1)!"
  }
}
```

## Span Elements

#### Links

- [link](https://example.com) `[link](https://example.com)`

#### Emphasis

- _italic_ `_italic_`
- **bold** `*bold*`

#### Code

- `code` `` `code` ``

#### Other

- ~~strikethrough~~ `~strikethrough~`

## Limited Subset

Posts types may use a limited subset of Tent Flavored Markdown for short texts. It corresponds to the existing [TFM](https://tent.io/docs/post-types#markdown) for Status posts.
