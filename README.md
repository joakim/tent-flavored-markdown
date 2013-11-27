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

## Block elements 

#### Newlines
- Newlines in TFM is the same as in standard markdown. Quoted from the Markdown spec: 
>A paragraph is simply one or more consecutive lines of text, separated by one or more blank lines. (A blank line is any line that looks like a blank line — a line containing nothing but spaces or tabs is considered blank.) Normal paragraphs should not be indented with spaces or tabs.

>The implication of the “one or more consecutive lines of text” rule is that Markdown supports “hard-wrapped” text paragraphs. This differs significantly from most other text-to-HTML formatters (including Movable Type’s “Convert Line Breaks” option) which translate every line break character in a paragraph into a `<br />` tag.

>When you do want to insert a `<br />` break tag using Markdown, you end a line with two or more spaces, then type return.

#### Headings

- Headings are the same as standard Markdown. They are indicated in one of several ways. First, you can indicate first and second level headings by putting any number of equal signs (`=`, heading level 1) or dashes (`-`, heading level 2) on a new line beneath the one that is your heading. 

Examples: 

```
Pizza tastes like turnips? Impossible!
======================================

Scientists say yes!
-------------------
```

Result: 
Pizza tastes like turnips? Impossible!
======================================

Scientists say yes!
-------------------

- Additionally, you can put up to six hashes (`#`) in front of your heading, with each hash representing one level deeper of heading. 

Examples: 

```
# Heading level 1
## heading level 2
### Heading level 3
#### Heading level 4
##### Heading level 5
###### Heading level 6
```

Result: 
# Heading level 1
## heading level 2
### Heading level 3
#### Heading level 4
##### Heading level 5
###### Heading level 6

#### Blockquotes
- Blockquotes are handled like they are in regular markdown. You can use a block quote by putting a greater-than symbol (`>`) at the beginning of every line you wanted to be a part of the block quote. 

Example:
```
> Quoted text
> Lorem ipsum,
> blah blah blah
> yadda yadda yadda
```

Result:
> Quoted text
> Lorem ipsum,
> blah blah blah
> yadda yadda yadda

- For nested block quotes, put a greater-than (`>`) two or more (how ever many nested levels you wanted) times.

Example: 

```
> Quoted text
> >Lorem ipsum,
> >blah blah blah
> yadda yadda yadda
```

Result:
> Quoted text
> >Lorem ipsum,
> >blah blah blah
> yadda yadda yadda

#### Links

###### Links with titles

- [link](https://example.com): `[link](https://example.com)`

###### Link indexing

- You can insert links with a double set of brackets that contain a title for the link as well as a referential ID (`[title][id])`). Then, anywhere in your document, you can put the reference: `[id]: https://example.com  "Optional Title Here"`.

###### Bare URLs

- If you put in a bare url like `https://example.com` without a title (e.g. `[link]` in `[link](https://example.com)`) it should be parsed as a URL. But, in some cases you want to set apart a URL from the surrounding punctuation. In this case, the URL can be defined by putting it in angle brackets, `<` and `>`, which allows us to differentiate it from punctuation around it.


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


## Limited Subset

Posts types may use a limited subset of Tent Flavored Markdown for short texts. It corresponds to the existing [TFM](https://tent.io/docs/post-types#markdown) for Status posts.
