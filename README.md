Issue 5110
================

## Introduction

When using Quarto variables, the markdown formatting is sometimes not
applied correctly
([\#5110](https://github.com/quarto-dev/quarto-cli/issues/5110)).

## Build

The `README.md` in this repo is generated using the following command:

``` sh
quarto render -o README.md -t gfm
```

This has been tested with Quarto v1.3.310.

## Examples

The following are all fetched from `_variables.yml` that is available in
this repository.

Below, we use the `{{< var ... >}}` syntax to include these variables in
the text:

------------------------------------------------------------------------

### Simple text

#### Code

    Some text

#### Expected result

Some text

#### Result

Some text

------------------------------------------------------------------------

### Bold text

#### Code

    bold text

#### Expected result

**bold text**

#### Result

**bold text**

------------------------------------------------------------------------

### Emphasis

#### Code

    emphasis

#### Expected result

*emphasis*

#### Result

*emphasis*

------------------------------------------------------------------------

### Bullets

#### Code

    This is item 1This is item 2

#### Expected result

- This is item 1
- This is item 2

#### Result

This is item 1This is item 2

------------------------------------------------------------------------

### Multiline

#### Code

    This is a multiline block. ¶ Keep in mind the indentation or add it explicitly in the YAML input.

#### Expected result

This is a multiline block.

Keep in mind the indentation or add it explicitly in the YAML input.

#### Result

This is a multiline block. ¶ Keep in mind the indentation or add it
explicitly in the YAML input.

------------------------------------------------------------------------

### Inline code

#### Code

    one two three

#### Expected result

`one two three`

#### Result

`one two three`

------------------------------------------------------------------------

### Code block

This is interesting, the multiline fenced code block is not rendered as
it should, although syntax highlighting is applied depending on the
markdown variant:

#### Code

    const a = [ 1, 2, 3 ]
    a.map( el => el + 1)

#### Expected result

``` js
const a = [ 1, 2, 3 ]
a.map( el =el + 1)
```

#### Result

`const a = [ 1, 2, 3 ]
a.map( el => el + 1)`

------------------------------------------------------------------------

### Title

#### Code

    ### A title

#### Expected result

### A title

#### Result

\### A title

------------------------------------------------------------------------

### Title in multiline string

#### Code

    Title in multiline string ¶ And some content after the title

#### Expected result

### Title in multiline string

And some content after the title

#### Result

Title in multiline string ¶ And some content after the title
