To content how the content in a page appears we use HTML tags to specify what kind of content each piece is, eg. a heading, a paragraph, a list etc.

Looking at the content in our homepage we can see that we have a heading, two single sentence paragraphs, and then a bulleted list of two items.

```
Tiny Cakes!
-----------

Welcome to my recipes web site all about Tiny Cakes!

Here are the recipes that we have:

 * Traditional cupcakes
 * Muffins
```

So lets add HTML to reflect that.  We call the act of adding HTML to content like that "marking up the document".

The terms "markup" & "marking-up" come from the book publishing world, where an editor would review the typed pages of a manuscript and write notes on the text about how it should be formatted for printing. https://en.wikipedia.org/wiki/Markup_language#Etymology

Replace the content (including the `<body>` tags) in `index.html` with the following:

```html
<body>
  <h1>Tiny Cakes!</h1>

  <p>
  Welcome to <em>my</em> recipes web site all
  about <strong>Tiny Cakes!</strong>
  </p>

  <p>
  Here are the recipes that we have:
  </p>

  <ul>
    <li>Traditional Cupcakes</li>
    <li>Muffins</li>
  </ul>

</body>
```

Refresh your browser and it should look a bit nicer.

[SCREENSHOT]

Much better, so lets talk about the HTML tags we used here.

`<h1>`
: This is a heading tag.  Specifically it is the **Level 1 Heading**.  There is also a `<h2>`, `<h3>` etc up to `<h6>`.  You use them to indicate headings and sub-headings. Each higher level indicates a deeper level & is usually slightly smaller each time.  

`<p>`
: The **paragraph** tag indicates a single block of text.  
<!-- Note that HTML doesn't display line breaks. -->

`<strong>`
: The **strong** tag indicates text that is important.  Browsers usually display this as bold by default.  

`<em>`
: The **emphasis** tag indicates text that requires emphasis (no really).  Browsers usually display this as italics by default.

`<ul>`
: The **unordered list** tag is used for bullet-points.

You can also create numbered lists with the **ordered list** tag `<ol>`.

`<li>`
: The **list item** tag is used for each item in an ordered or unordered list.

And that is mostly as hard as HTML gets really.  There are a lot more tags than just these few but the same basic concept applies:

1. You use HTML tags to specify how a web browser should treat different pieces of content.
2. You use opening & closing tags to indicate where to start and finish applying it.

## Nesting tags & Inline vs Block tags

There are two primary types of tags: **inline** and **block**.

You can think of block tags as always starting on a new line and taking up the whole line.  Inline tags don't start a new line and only take up the minimum space required.  (it is more complicated than that but it's not completely inaccurate)

All of the tags we used above except for `<em>` & `<strong>` are block tags.

Notice how we used `<em>` and `<strong>` inside of a `<p>`?  We call this **nesting** tags.

You *can* nest any tags however you want.  But they don't always complete sense even if they might still look how you expect.  

For example:

```html
<p>
Welcome to <em>my</em> recipes web site all
about <strong>Tiny Cakes!</strong>
<h2>Recipes:</h2>
Here are the recipes that we have:
</p>
```

But this will create some problems for you.  Browsers are a bit inconsistent with handling weird combinations like this and your CSS will probably not like it either as we will see later.

Some tags must be nested inside others, like `<li>` which must be inside of `<ol>` or `<ul>`


## Hyperlinks

There is one more super important HTML tag we need to mention before we head on to the next step: `<a>` the **anchor** tag AKA the hyperlink tag.

The `<a>` tag is how we create hyperlinks, ie links to other pages on our site or on the internet.

Lets make our list of recipes into a list of hyperlinks to our other recipes pages.  Replace our `<ul>` with:

```html
<ul>
  <li><a href="traditional-cupcakes.html">Traditional Cupcakes</a></li>
  <li><a href="muffins.html">Muffins</a></li>
</ul>
```

Now refresh your page and the list should be hyperlinks, usually blue and underlined by default.

[SCREENSHOT]

If you click on one of them, your browser will navigate to that page and you'll see the unformatted content because we haven't added any markup to those yet.  Click the back button in your browser to get back to the original page.

Notice the `href="muffins.html"` part of the tag?  This is called an attribute.  Specifically it is the **hypertext reference** attribute.  The quotes contain the URL that clicking on the link will navigate to.  Here we just put the file name of the page with nothing else because it's in the same directory.

If you want to link to a different site you have to put the whole URL like:

```html
<a href="http://nodegirls.com.au/brisbane.html">Node Girls: Brisbane</a>
```

Some tags require attributes for specific features.

Ok lets move on to marking up our recipes pages.
