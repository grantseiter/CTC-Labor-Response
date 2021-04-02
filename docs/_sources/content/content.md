Technical Description
=======================

There are many ways to write content in Jupyter Book. This short section
covers a few tips for how to do so.

Under the American Rescue Plan, the CTC was temporarily increased (for 2021) to $3,600 for each child under age six and $3,000 for each child age six to seventeen. The credit was also made fully refundable, which means that the full credit is available to taxpayers even if its value exceeds their income tax liability. For example, a household with two young children and little or no wage income will get a $7,200 credit under the American Rescue Plan. Previously, only $1,400 of the credit was refundable, thereby capping the maximum refundable benefit for the same family at $2,800.

In choosing how much to work, people respond to incentives that are partly determined by taxes on income from that work and by government benefits that vary with income. Those responses play a critical role in CBO’s analysis of the effects of changes in fiscal policy on economic outcomes.
CBO uses two models of the economy to analyze the medium- and long-term effects of federal tax and spending policies: a Solow-type growth model and a life-cycle growth model. The models take different approaches toward capturing the ways in which the supply of labor responds to changes in fiscal policy. The Solow-type growth model uses estimates of how much the labor supply changes at a given point in time in response to a change in after-tax compensation that would result, for example, from a change in tax rates. The life-cycle growth model uses estimates of the responsiveness of the labor supply that depend on how people expect their after-tax compensation to change over time. CBO reviewed the extensive research literature on the magnitude of those responses, and this report describes the values the agency will be using in future analyses.


Whether you write your book's content in Jupyter Notebooks (`.ipynb`) or
in regular markdown files (`.md`), you'll write in the same flavor of markdown
called **MyST Markdown**.

## What is MyST?

MyST stands for "Markedly Structured Text". It
is a slight variation on a flavor of markdown called "CommonMark" markdown,
with small syntax extensions to allow you to write **roles** and **directives**
in the Sphinx ecosystem.

## What are roles and directives?

Roles and directives are two of the most powerful tools in Jupyter Book. They
are kind of like functions, but written in a markup language. They both
serve a similar purpose, but **roles are written in one line**, whereas
**directives span many lines**. They both accept different kinds of inputs,
and what they do with those inputs depends on the specific role or directive
that is being called.

### Using a directive

At its simplest, you can insert a directive into your book's content like so:

````
```{mydirectivename}
My directive content
```
````

This will only work if a directive with name `mydirectivename` already exists
(which it doesn't). There are many pre-defined directives associated with
Jupyter Book. For example, to insert a note box into your content, you can
use the following directive:

````
```{note}
Here is a note
```
````

This results in:

```{note}
Here is a note
```

In your built book.

For more information on writing directives, see the
[MyST documentation](https://myst-parser.readthedocs.io/).


### Using a role

Roles are very similar to directives, but they are less-complex and written
entirely on one line. You can insert a role into your book's content with
this pattern:

```
Some content {rolename}`and here is my role's content!`
```

Again, roles will only work if `rolename` is a valid role's name. For example,
the `doc` role can be used to refer to another page in your book. You can
refer directly to another page by its relative path. For example, the
role syntax `` {doc}`intro` `` will result in: {doc}`intro`.

For more information on writing roles, see the
[MyST documentation](https://myst-parser.readthedocs.io/).


### Adding a citation

You can also cite references that are stored in a `bibtex` file. For example,
the following syntax: `` {cite}`holdgraf_evidence_2014` `` will render like
this: {cite}`holdgraf_evidence_2014`.

Moreoever, you can insert a bibliography into your page with this syntax:
The `{bibliography}` directive must be used for all the `{cite}` roles to
render properly.
For example, if the references for your book are stored in `references.bib`,
then the bibliography is inserted with:

````
```{bibliography}
```
````

Resulting in a rendered bibliography that looks like:

```{bibliography}
```


### Executing code in your markdown files

If you'd like to include computational content inside these markdown files,
you can use MyST Markdown to define cells that will be executed when your
book is built. Jupyter Book uses *jupytext* to do this.

First, add Jupytext metadata to the file. For example, to add Jupytext metadata
to this markdown page, run this command:

```
jupyter-book myst init markdown.md
```

Once a markdown file has Jupytext metadata in it, you can add the following
directive to run the code at build time:

````
```{code-cell}
print("Here is some code to execute")
```
````

When your book is built, the contents of any `{code-cell}` blocks will be
executed with your default Jupyter kernel, and their outputs will be displayed
in-line with the rest of your content.

For more information about executing computational content with Jupyter 