# Issue …

## Introduction

Using [Quarto
variables](https://quarto.org/docs/authoring/variables.html) makes a lot
of sense when dealing with customizations. Variables can include
markdown, but in our experience it’s limited to hyperlinks and some
basic formatting.

This has been tested with Quarto v1.3.310.

The `README.md` in this repo is generated using the following command:

``` sh
quarto render -o README.md -t gfm
```

## Examples

The following are all fetched from `_variables.yml` that is available in
this repository.

Below, we use the `{{< var ... >}}` syntax to include these variables in
the text:

### Simple text

A simple string variable:

<div class="bg-light">

Some text

</div>

### Bold text

<div class="bg-light">

**bold text**

</div>

### Emphasis

<div class="bg-light">

*emphasis*

</div>

### Bullets

A bullet list:

<div class="bg-light">

This is item 1This is item 2

</div>

### Multiline

<div class="bg-light">

This is a multiline block.  
Keep in mind the indentation or add it explicitly in the YAML input.

</div>

### Code

This is interesting, the multiline fenced code block is not rendered as
it should, although syntax highlighting is applied:

<div class="bg-dark">

`const a = [ 1, 2, 3 ]
a.map( el => el + 1)`

</div>

### Title

<div class="bg-light">

\### A title

</div>

### Title in multiline string

<div class="bg-light">

Title in multiline string  
And some content after the title

</div>
