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

###### Links with titles

- [link](https://example.com): `[link](https://example.com)`

###### Bare URLs

- If you put in a bare url like `https://example.com` without a title (e.g. `[link]` in `[link](https://example.com)`) it can be defined by putting it angle brackets, `<` and `>`, which allows us to differentiate it from punctuation around it.

###### Link indexing
- You can insert links with a double set of brackets that contain a title for the link as well as a referential ID (`[title][id]). Then, anywhere in your document, you can put the reference: 


#### Emphasis

- _italic_: `_italic_`
- **bold**: `*bold*`

#### Code

- inline `code`: `` `code` ``
- block `code`: 
  <pre><code>\`\`\`
code
\`\`\`</code></pre>

#### Other (Span Elements)

- ~~strikethrough~~: `~strikethrough~`

## Other (General)

#### Newlines
- Newlines in TFM is the same as in standard markdown. Quoted from the Markdown spec: 
>A paragraph is simply one or more consecutive lines of text, separated by one or more blank lines. (A blank line is any line that looks like a blank line — a line containing nothing but spaces or tabs is considered blank.) Normal paragraphs should not be indented with spaces or tabs.

>The implication of the “one or more consecutive lines of text” rule is that Markdown supports “hard-wrapped” text paragraphs. This differs significantly from most other text-to-HTML formatters (including Movable Type’s “Convert Line Breaks” option) which translate every line break character in a paragraph into a `<br />` tag.

>When you do want to insert a `<br />` break tag using Markdown, you end a line with two or more spaces, then type return.

## Limited Subset

Posts types may use a limited subset of Tent Flavored Markdown for short texts. It corresponds to the existing [TFM](https://tent.io/docs/post-types#markdown) for Status posts.
