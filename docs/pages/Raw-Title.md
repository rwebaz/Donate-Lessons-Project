---
title: Raw Title
layout: default
excerpt: Gists can be embedded into Markdown (.md) pages ...
hint: The Solution to the MD033 lint warning when embedding a script tag from GitHub Gists in the body of a Markdown page.
repo: Donate-Lessons-Project
ver_date: 11-26-19
navigation_weight: 8
categories: page
raw: https://gist.githubusercontent.com/rwebaz/cee767ff589050e79c8d59edf6b7e084/raw/873984fc5a627828a88f797632ed87a3f6dc2777/Turning-Comments-Into-Gists.md
---
{% include toc.md %}

## Script Tag

> **Hint**. {{ page.hint }}

More to come ...

### How to embed a script tag from GitHub Gists in the body of a Markdown page

Create entry in `User Settings`, `Markdownlint Configuration Object` as follows:

"MD033": {"allowed_elements": ["script"]} when crafting your page in Visual Studio Code.

## Import Code

## Embed A Gist

Here is our gist captured from our *public* search at GitHub Gists.

```html
<script src="https://gist.github.com/rwebaz/cee767ff589050e79c8d59edf6b7e084.js"></script>
```

When we attempt to render same ...

Our trusty Markdown [linter](https://github.com/DavidAnson/markdownlint/blob/master/doc/Rules.md){:title="Click to Visit the Markdown Lint Rules page of the Markdown Lint Project at GitHub pages by David Anson"}{:target="_blank"} as provided by [David Anson](https://dlaa.me/blog/post/markdownlint){:title="Click to Visit the Web-log Markdown page of David Anson"}{:target="_blank"} sez "Nyet!"

Something about Rule MD033 ( no inline html allowed in the body of a markdown (.md) file ).

### Solution

Rationale: Raw HTML is allowed in markdown, but this rule is included for those who want their documents to only include "pure" markdown, or for those who are rendering markdown documents in something other than HTML.

Note: To allow specific HTML elements, use the 'allowed_elements' parameter.

## Markdownlint Configuration Object

How to Craft a `json` entry to your `Markdownlint Configuration Object` within the `User Settings` file of your instance of the Visual Studio Code IDE ...

Create the Object snippet, as follows:

```liquid
{% raw %}
// Begin Markdownlint Configuration Object
"markdownlint.config": {
  "MD013": false,
  "MD033": {"allowed_elements": ["script"]}
}// End Markdownlint Configuration Object
{% endraw %}
```

**Note**. The Markdownlint Configuration Object, or MCO comes pre-configured with the first entry `"MD013": false` upon install of the Markdownlint extension ver `0.13.0`.

The `User Settings` file of your instance of the Visual Studio Code IDE is a `Json` file.

And, the first entry of your Markdownlint Configuration Object, or [MCO](http://thisdavej.com/build-an-amazing-markdown-editor-using-visual-studio-code-and-pandoc/){:title='Markdownlint Configuration Object'}{:target='_blank'} is a `key - value` pair.

Here, the editor recognizes the error code key `MD013` and the boolean value `false`.

The next entry within our Markdownlint Configuration Object, or [MCO](http://thisdavej.com/build-an-amazing-markdown-editor-using-visual-studio-code-and-pandoc/){:title='Markdownlint Configuration Object'}{:target='_blank'} is also a `key - value` pair.

Here, the editor recognizes the error code key `MD033` and an object value `{...}` that houses the required parameter of `allowed_elements` ...

And, an array of html tags `[...]` that can be allowed in the body of the the subject Markdown (.md) page without triggering a *lint warning*.

In this case the array `[...]` has one (1) html tag namely the html `script` tag.

This will allow us to embed gists into our Markdown (.md) page straight away without modification, as follows:

<script src="https://gist.github.com/rwebaz/cee767ff589050e79c8d59edf6b7e084.js"></script>

## Last Subtitle

## GitHub Gists

To gist or not to gist. That is the $64 question ...

**GitHub Gists** are `Single ( or, multiple ) Simple Markdown Files` with *repo-like* qualities that can be forked or cloned ( if public ).

Otherwise, not if private.

Kinda like a fancy scratch pad that can be shared.

Similar to this comment scratch pad that I am typing on now, but a bit more elaborate.

Whereas, an *official*, full GitHub repo is a full blown repository of source code `src`, supporting documents ( markdown or html, or both ) `docs` or `root`, images `png`, `ico`, `svg`, and a `config.sys` file for running Yaml variables hosted on a Jekyll server.

Does a simple Gist file support Yaml front matter?

Me thinks not.

From the official GitHub Gist documentation ...

The gist editor is powered by [CodeMirror][1].

However, you can copy a public Gist ( or, a private Gist if the owner has granted you access via a link to the private Gist ) ...

And, you can then embed that public Gist into an "official" repo `page.md` using Visual Studio Code, as follows:

"You can embed a gist in any text field that supports Javascript, such as a blog post."

"To get the `embed` code, click the clipboard icon next to the `Embed URL` button of a gist."

Now, that's a cool feature.

Makes me want to search ( discover ) other peoples' gists, or **OPG** and incorporate their "public" work into my full-blown working repos.

"You can discover the PUBLIC gists others have created by going to the gist home page and clicking on the link ...

- [All Gists](https://gist.github.com/discover){:title='Click to Review the Discover Feature at GitHub Gists'}{:target='_blank'}."

I suppose if I do find something beneficial, I can always ping-back, or cite that source if I do use the work in my full-blown working repos.

Where is the implicit license posted for all gists made public by their authors?

Robert

P.S. This is a good comment. I think I will turn this into a `gist` and make it publicly searchable over at GitHub Gists.

**Note**. When embedding the `<script></script>` html tag within the body of a Markdown (.md) file, you may get a warning "MD033" from your [linter][2].

This should not, however, affect the rendering of the data ( src ) called from within the `script` tag.

To change the default warning flag to accommodate the called contents of a `script` tag from within Visual Studio Code, add an entry to the *Markdownlint Configuration Object* within the `User Settings` Json file, as follows:

    // Begin Markdownlint Configuration Object
    "markdownlint.config": {
      "MD013": false,
      "MD033": {"allowed_elements": ["script"]}
    }// End Markdownlint Configuration Object

**Note**. Solution derived from [GitHub Commit by David Anson](https://github.com/DavidAnson/markdownlint/commit/fb31bb5f350ce76550377c6d84b3834aee269ee8){:title='Click to Review the GitHub Commit by David Anson'}{:target='_blank'}.

[1]: https://help.github.com/articles/about-gists/
[2]: https://github.com/DavidAnson/markdownlint/blob/master/doc/Rules.md
[3]: https://github.com/DavidAnson/markdownlint/commit/fb31bb5f350ce76550377c6d84b3834aee269ee8
[4]: https://gist.github.com/discover

## Permalink to this gist

- The raw gist of [Turning Comments Into Gists]({{ page.raw }}){:title='Click to Visit the raw gist of Turning Comments Into Gists at GitHub Gists'}{:target='_blank'} at GitHub Gists.

## Last Subtitle

More to come ...

***

**Note**. The above synopsis was derived from an article written by Blank Author [[1](#BLANKAUTHOR){:.red}].

1. {:#BLANKAUTHOR}[A Narrative of Psychology by Blank Author, Jan #1999](http://cowles.yale.edu/sites/default/files/files/pub/d20/d2069.pdf){:title="Click to Review ..."}{:target="_blank"}

***

{% include patreon-link.md %}
