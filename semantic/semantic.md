# most used HTML semantic elements

https://developer.mozilla.org/en-US/docs/Glossary/Semantics#semantics_in_html

## article

The **`<article>`**[HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) element represents a self-contained composition in a document, page, application, or site, which is intended to be independently distributable or reusable (e.g., in syndication). Examples include: a forum post, a magazine or newspaper article, or a blog entry, a product card, a user-submitted comment, an interactive widget or gadget, or any other independent item of content.

A given document can have multiple articles in it; for example, on a blog that shows the text of each article one after another as the reader scrolls, each post would be contained in an `<article>` element, possibly with one or more `<section>`s within.

### usage notes

- Each `<article>` should be identified, typically by including a heading ([`<h1>`-`<h6>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements) element) as a child of the `<article>` element.
- When an `<article>` element is nested, the inner element represents an article related to the outer element. For example, the comments of a blog post can be `<article>` elements nested in the `<article>` representing the blog post.
- Author information of an `<article>` element can be provided through the [`<address>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/address) element, but it doesn't apply to nested `<article>` elements.
- The publication date and time of an `<article>` element can be described using the [`datetime`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/time#attr-datetime) attribute of a [`<time>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/time) element. _Note that the [`pubdate`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/time#attr-pubdate) attribute of [`<time>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/time) is no longer a part of the [W3C](https://developer.mozilla.org/en-US/docs/Glossary/W3C) [HTML5](https://developer.mozilla.org/en-US/docs/Glossary/HTML5) standard._

## aside

The **`<aside>`** [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) element represents a portion of a document whose content is only indirectly related to the document's main content. Asides are frequently presented as sidebars or call-out boxes.

### usage notes

- Do not use the `<aside>` element to tag parenthesized text, as this kind of text is considered part of the main flow.

## details

The **`<details>`**[HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) element creates a disclosure widget in which information is visible only when the widget is toggled into an "open" state. A summary or label must be provided using the [`<summary>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/summary) element.

A disclosure widget is typically presented onscreen using a small triangle which rotates (or twists) to indicate open/closed status, with a label next to the triangle. The contents of the `<summary>` element are used as the label for the disclosure widget.

A `<details>` widget can be in one of two states. The default _closed_ state displays only the triangle and the label inside `<summary>` (or a [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)-defined default string if no `<summary>`).

When the user clicks on the widget or focuses it then presses the space bar, it "twists" open, revealing its contents. The common use of a triangle which rotates or twists around to represent opening or closing the widget is why these are sometimes called "twisties".

You can use CSS to style the disclosure widget, and you can programmatically open and close the widget by setting/removing its [`open`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details#attr-open) attribute. Unfortunately, at this time there's no built-in way to animate the transition between open and closed.

By default when closed, the widget is only tall enough to display the disclosure triangle and summary. When open, it expands to display the details contained within.

Fully standards-compliant implementations automatically apply the CSS `<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/display"><code>display</code></a>: list-item` to the [`<summary>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/summary) element. You can use this to customize its appearance further. See [Customizing the disclosure widget](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details#customizing_the_disclosure_widget) for further details.

### open

This Boolean attribute indicates whether or not the details — that is, the contents of the `<details>` element — are currently visible. The details are shown when this attribute exists, or hidden when this attribute is absent. By default this attribute is absent which means the details are not visible.

### events

In addition to the usual events supported by HTML elements, the `<details>` element supports the `<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLDetailsElement/toggle_event" title="/en-US/docs/Web/Events/toggle">toggle</a>` event, which is dispatched to the `<details>` element whenever its state changes between open and closed. It is sent _after_ the state is changed, although if the state changes multiple times before the browser can dispatch the event, the events are coalesced so that only one is sent.

You can use an event listener for the `toggle` event to detect when the widget changes state:

```
details.addEventListener("toggle", event => {
  if (details.open) {
    /* the element was toggled open */
  } else {
    /* the element was toggled closed */
  }
});
```

### examples

#### simple disclosure example

This example shows a simple `<details>` element with a `<summary>`.

```
<details>
  <summary>System Requirements</summary>
  <p>Requires a computer running an operating system. The computer
  must have some memory and ideally some kind of long-term storage.
  An input device as well as some form of output device is
  recommended.</p>
</details>
```

#### open disclosure box

To start the `<details>` box in its open state, add the Boolean `open` attribute:

```
<details open>
  <summary>System Requirements</summary>
  <p>Requires a computer running an operating system. The computer
  must have some memory and ideally some kind of long-term storage.
  An input device as well as some form of output device is
  recommended.</p>
</details>
```

#### customizing the disclosure widget

The disclosure triangle itself can be customized, although this is not as broadly supported. There are variations in how browsers support this customization due to experimental implementations as the element was standardized, so we'll have to use multiple approaches for a while.

The [`<summary>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/summary) element supports the [`list-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style) shorthand property and its longhand properties, such as [`list-style-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type), to change the disclosure triangle to whatever you choose (usually with [`list-style-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-image)). For example, we can remove the disclosure widget icon by setting `list-style: none`.

## figcaption

The **`<figcaption>`** [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) element represents a caption or legend describing the rest of the contents of its parent [`<figure>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/figure) element.

## figure

The **`<figure>`** [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) element represents self-contained content, potentially with an optional caption, which is specified using the [`<figcaption>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/figcaption) element. The figure, its caption, and its contents are referenced as a single unit.

### attributes

This element only includes the [global attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes).

### usage notes

- Usually a `<figure>` is an image, illustration, diagram, code snippet, etc., that is referenced in the main flow of a document, but that can be moved to another part of the document or to an appendix without affecting the main flow.
- Being a [sectioning root](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements#sectioning_roots), the outline of the content of the `<figure>` element is excluded from the main outline of the document.
- A caption can be associated with the `<figure>` element by inserting a [`<figcaption>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/figcaption) inside it (as the first or the last child). The first `<figcaption>` element found in the figure is presented as the figure's caption.

### example

```
<!-- Image with a caption -->
<figure>
  <img
  src="favicon-192x192.png"
  alt="The beautiful MDN logo.">
  <figcaption>MDN Logo</figcaption>
</figure>
```

## footer

The **`<footer>`** [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) element represents a footer for its nearest [sectioning content](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#sectioning_content) or [sectioning root](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements#sectioning_root) element. A `<footer>` typically contains information about the author of the section, copyright data or links to related documents.

### usage notes

- Enclose information about the author in an [`<address>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/address) element that can be included into the `<footer>` element.
- The `<footer>` element is not sectioning content and therefore doesn't introduce a new section in the [outline](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements).

### examples

```
<footer>
  Some copyright info or perhaps some author
  info for an <article>?
</footer>
```

### accessibility concerns

Prior to the release of Safari 13, the `contentinfo` [landmark role](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics#signpostslandmarks) was not properly exposed by [VoiceOver](https://help.apple.com/voiceover/info/guide/). If needing to support legacy Safari browsers, add `role="contentinfo"` to the `footer` element to ensure the landmark will be properly exposed.

- Related: [WebKit Bugzilla: 146930 – AX: HTML native elements (header, footer, main, aside, nav) should work the same as ARIA landmarks, sometimes they don&#39;t](https://bugs.webkit.org/show_bug.cgi?id=146930)

## header

The **`<header>`** [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) element represents introductory content, typically a group of introductory or navigational aids. It may contain some heading elements but also a logo, a search form, an author name, and other elements.

### usage notes

The `<header>` element is not sectioning content and therefore does not introduce a new section in the [outline](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements). That said, a `<header>` element is intended to usually contain the surrounding section's heading (an `h1`–`h6` element), but this is **not** required.

#### historical usage

Although the `<header>` element didn't make its way into specifications until [HTML5](https://developer.mozilla.org/en-US/docs/Glossary/HTML5), it actually existed at the very beginning of HTML. As seen in [the very first website](http://info.cern.ch/), it was originally used as the `<head>` element. At some point, it was decided to use a different name. This allowed `<header>` to be free to fill a different role later on.

### examples

#### page header

```
<header>
  <h1>Main Page Title</h1>
  <img src="mdn-logo-sm.png" alt="MDN logo">
</header>
```

#### article header

```
<article>
  <header>
    <h2>The Planet Earth</h2>
    <p>Posted on Wednesday, <time datetime="2017-10-04">4 October 2017</time> by Jane Smith</p>
  </header>
  <p>We live on a planet that's blue and green, with so many things still unseen.</p>
  <p><a href="https://example.com/the-planet-earth/">Continue reading....</a></p>
</article>
```

### accessibility

The `<header>` element defines a [`banner`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/banner_role) landmark when its context is the [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body) element. The HTML header element is not considered a banner landmark when it is descendant of an [`<article>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article), [`<aside>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/aside), [`<main>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/main), [`<nav>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/nav), or [`<section>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section) element.

## main

The **`<main>`** [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) element represents the dominant content of the [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body) of a document. The main content area consists of content that is directly related to or expands upon the central topic of a document, or the central functionality of an application.

### usage notes

The content of a `<main>` element should be unique to the document. Content that is repeated across a set of documents or document sections such as sidebars, navigation links, copyright information, site logos, and search forms shouldn't be included unless the search form is the main function of the page.

`<main>` doesn't contribute to the document's outline; that is, unlike elements such as [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body), headings such as [`<h2>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements), and such, `<main>` doesn't affect the [DOM&#39;s](https://developer.mozilla.org/en-US/docs/Glossary/DOM) concept of the structure of the page. It's strictly informative.

### example

```
<!-- other content -->

<main>
  <h1>Apples</h1>
  <p>The apple is the pomaceous fruit of the apple tree.</p>

  <article>
    <h2>Red Delicious</h2>
    <p>These bright red apples are the most common found in many
    supermarkets.</p>
    <p>... </p>
    <p>... </p>
  </article>

  <article>
    <h2>Granny Smith</h2>
    <p>These juicy, green apples make a great filling for
    apple pies.</p>
    <p>... </p>
    <p>... </p>
  </article>
</main>

<!-- other content -->
```

### accessibility concerns

#### landmark

The `<main>` element behaves like a [`main` landmark](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/main_role) role. [Landmarks](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques#landmark_roles) can be used by assistive technology to quickly identify and navigate to large sections of the document. Prefer using the `<main>` element over declaring `role="main"`, unless there are [legacy browser support concerns](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/main#browser_compatibility).

#### skip navigation

Skip navigation, also known as "skipnav", is a technique that allows an assistive technology user to quickly bypass large sections of repeated content (main navigation, info banners, etc.). This lets the user access the main content of the page faster.

Adding an [`id`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-id) attribute to the `<main>` element lets it be a target of a skip navigation link.

```
<body>
  <a href="#main-content">Skip to main content</a>

  <!-- navigation and header content -->

  <main id="main-content">
    <!-- main page content -->
  </main>
</body>
```

[- WebAIM: &#34;Skip Navigation&#34; Links](https://webaim.org/techniques/skipnav/)

#### reader mode

Browser reader mode functionality looks for the presence of the `<main>` element, as well as [heading](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements) and [content sectioning elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Element#content_sectioning) when converting content into a specialized reader view.

- [Building websites for Safari Reader Mode and other reading apps.](https://medium.com/@mandy.michael/building-websites-for-safari-reader-mode-and-other-reading-apps-1562913c86c9)

### browser compatibilty

To support Internet Explorer 11 and lower, you can add an [ARIA](https://developer.mozilla.org/en-US/docs/Glossary/ARIA) role of `"main"` to the `<main>` element. But understand that the ARIA in HTML specification states that `role="main"` shouldn't actually be used with the `<main>` element, and the W3C validator will report a warning for it. However, Internet Explorer 11 and lower will otherwise not correctly expose the `<main>` element to screen readers such JAWS unless the element also has a `role="main"` attribute.

## mark

The **`<mark>`** [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) element represents text which is **marked** or **highlighted** for reference or notation purposes, due to the marked passage's relevance or importance in the enclosing context.

### usage notes

Typical use cases for `<mark>` include:

- When used in a quotation ([`<q>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/q)) or block quote ([`<blockquote>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote)), it generally indicates text which is of special interest but is not marked in the original source material, or material which needs special scrutiny even though the original author didn't think it was of particular importance. Think of this like using a highlighter pen in a book to mark passages that you find of interest.
- Otherwise, `<mark>` indicates a portion of the document's content which is likely to be relevant to the user's current activity. This might be used, for example, to indicate the words that matched a search operation.
- Don't use `<mark>` for syntax highlighting purposes; instead, use the [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) element with appropriate CSS applied to it.

**Note:** Don't confuse `<mark>` with the [`<strong>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/strong) element; `<mark>` is used to denote content which has a degree of _relevance_ , while `<strong>` indicates spans of text of _importance_ .

### examples

#### marking text of interest

In this first example, a `<mark>` element is used to mark some text within a quote which is of particular interest to the user.

```
<blockquote>
  It is a period of civil war. Rebel spaceships, striking from a
  hidden base, have won their first victory against the evil
  Galactic Empire. During the battle, <mark>Rebel spies managed
  to steal secret plans</mark> to the Empire's ultimate weapon,
  the DEATH STAR, an armored space station with enough power to
  destroy an entire planet.
</blockquote>
```

#### identifying context-sensitive passages

This example demonstrates using `<mark>` to mark search results within a passage.

```
<p>It is a dark time for the Rebellion. Although the Death
Star has been destroyed, <mark class="match">Imperial</mark>
troops have driven the Rebel forces from their hidden base and
pursued them across the galaxy.</p>

<p>Evading the dreaded <mark class="match">Imperial</mark>
Starfleet, a group of freedom fighters led by Luke Skywalker
has established a new secret base on the remote ice world of
Hoth.</p>
```

To help distinguish the use of `<mark>` for search results from other potential usage, this example applies the custom class `"match"` to each match.

### accessibility concerns

The presence of the `mark` element is not announced by most screen reading technology in its default configuration. It can be made to be announced by using the CSS [`content`](https://developer.mozilla.org/en-US/docs/Web/CSS/content) property, along with the [`::before`](https://developer.mozilla.org/en-US/docs/Web/CSS/::before) and [`::after`](https://developer.mozilla.org/en-US/docs/Web/CSS/::after) pseudo-elements.

```
mark::before,
mark::after {
  clip-path: inset(100%);
  clip: rect(1px, 1px, 1px, 1px);
  height: 1px;
  overflow: hidden;
  position: absolute;
  white-space: nowrap;
  width: 1px;
}

mark::before {
  content: " [highlight start] ";
}

mark::after {
  content: " [highlight end] ";
}
```

Some people who use screen readers deliberately disable announcing content that creates extra verbosity. Because of this, it is important to not abuse this technique and only apply it in situations where not knowing content has been highlighted would adversely affect understanding.

- [Short note on making your mark (more accessible) | The Paciello Group](https://developer.paciellogroup.com/blog/2017/12/short-note-on-making-your-mark-more-accessible/)
- [Tweaking Text Level Styles | Adrian Roselli](https://adrianroselli.com/2017/12/tweaking-text-level-styles.html)

## nav

The **`<nav>`** [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) element represents a section of a page whose purpose is to provide navigation links, either within the current document or to other documents. Common examples of navigation sections are menus, tables of contents, and indexes.

### usage notes

- It's not necessary for all links to be contained in a `<nav>` element. `<nav>` is intended only for major block of navigation links; typically the [`<footer>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/footer) element often has a list of links that don't need to be in a [`<nav>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/nav) element.
- A document may have several [`<nav>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/nav) elements, for example, one for site navigation and one for intra-page navigation. [`aria-labelledby`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-labelledby) can be used in such case to promote accessibility, see [example](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements#labeling_section_content).
- User agents, such as screen readers targeting disabled users, can use this element to determine whether to omit the initial rendering of navigation-only content.

### examples

In this example, a `<nav>` block is used to contain an unordered list ([`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul)) of links. With appropriate CSS, this can be presented as a sidebar, navigation bar, or drop-down menu.

```
<nav class="menu">
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Contact</a></li>
  </ul>
</nav>
```

The semantics of the `nav` element is that of providing links. However a `nav` element doesn't have to contain a list, it can contain other kinds of content as well. In this navigation block, links are provided in prose:

```
<nav>
  <h2>Navigation</h2>
  <p>You are on my home page. To the north lies <a href="/blog">my
  blog</a>, from whence the sounds of battle can be heard. To the east
  you can see a large mountain, upon which many <a
  href="/school">school papers</a> are littered. Far up thus mountain
  you can spy a little figure who appears to be me, desperately
  scribbling a <a href="/school/thesis">thesis</a>.</p>
  <p>To the west are several exits. One fun-looking exit is labeled <a
  href="https://games.example.com/">"games"</a>. Another more
  boring-looking exit is labeled <a
  href="https://isp.example.net/">ISP™</a>.</p>
  <p>To the south lies a dark and dank <a href="/about">contacts
  page</a>. Cobwebs cover its disused entrance, and at one point you
  see a rat run quickly out of the page.</p>
</nav>
```

## section

The **`<section>`** [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) element represents a generic standalone section of a document, which doesn't have a more specific semantic element to represent it. Sections should always have a heading, with very few exceptions.

### usage notes

As mentioned above, `<section>` is a generic sectioning element, and should only be used if there isn't a more specific element to represent it. As an example, a navigation menu should be wrapped in a [`<nav>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/nav) element, but a list of search results or a map display and its controls don't have specific elements, and could be put inside a `<section>`.

Also consider these cases:

- If the contents of the element represent a standalone, atomic unit of content that makes sense syndicated as a standalone piece (e.g. a blog post or blog comment, or a newspaper article), the [`<article>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article) element would be a better choice.
- If the contents represent useful tangential information that works alongside the main content, but is not directly part of it (like related links, or an author bio), use an [`<aside>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/aside).
- If the contents represent the main content area of a document, use [`<main>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/main).
- If you are only using the element as a styling wrapper, use a [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div). A rule of thumb is that a `<section>` should logically appear in the outline of a document.

To reiterate, each `<section>` should be identified, typically by including a heading ([`<h1>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements)-[`<h6>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements) element) as a child of the `<section>` element, wherever possible. See below for examples of where you might see a `<section>` without a heading.

### examples

#### simple usage example

##### before

```
<div>
  <h2>Heading</h2>
  <p>Bunch of awesome content</p>
</div>
```

##### after

```
<section>
  <h2>Heading</h2>
  <p>Bunch of awesome content</p>
</section>
```

### using a section without heading

Circumstances where you might see `<section>` used without a heading are typically found in web application/UI sections rather than in traditional document structures. In a document, it doesn't really make any sense to have a separate section of content without a heading to describe its contents. Such headings are useful for all readers, but particularly useful for users of assistive technologies like screenreaders, and they are also good for SEO.

Consider however a secondary navigation mechanism. If the global navigation is already wrapped in a `<nav>` element, you could conceivably wrap a previous/next menu in a `<section>`:

```
<section>
  <a href="#">Previous article</a>
  <a href="#">Next article</a>
</section>
```

Or what about some kind of button bar for controlling your app? This might not necessarily want a heading, but it is still a distinct section of the document:

```
<section>
  <button class="reply">Reply</button>
  <button class="reply-all">Reply to all</button>
  <button class="fwd">Forward</button>
  <button class="del">Delete</button>
</section>
```

Sections with no headings do not appear in the document outline. If you did want to force the inclusion of such an HTML block inside the document outline but not affect the visual output in any way, you could include a heading but hide it:

```
<section>
  <h2 class="hidden">Controls</h2>
  <button class="reply">Reply</button>
  <button class="reply-all">Reply to all</button>
  <button class="fwd">Forward</button>
  <button class="del">Delete</button>
</section>
```

Make sure to use some assistive technology and screenreader-friendly CSS to hide it, like so:

```
.hidden {
  position: absolute;
  top: -9999px;
  left: -9999px;
}
```

Depending on the content, including a heading could also be good for SEO, so it is an option to consider.

## summary

The **`<summary>`** [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) element specifies a summary, caption, or legend for a [`<details>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details) element's disclosure box. Clicking the `<summary>` element toggles the state of the parent `<details>` element open and closed.

### usage notes

The `<summary>` element's contents can be any heading content, plain text, or HTML that can be used within a paragraph.

A `<summary>` element may _only_ be used as the first child of a `<details>` element. When the user clicks on the summary, the parent `<details>` element is toggled open or closed, and then a `<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLDetailsElement/toggle_event" title="/en-US/docs/Web/Events/toggle">toggle</a>` event is sent to the `<details>` element, which can be used to let you know when this state change occurs.

#### default label text

If a `<details>` element's first child is not a `<summary>` element, the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) will use a default string (typically "Details") as the label for the disclosure box.

#### default style

Per the HTML specification, the default style for `<summary>` elements includes `display: list-item`. This makes it possible to change or remove the icon displayed as the disclosure widget next to the label from the default, which is typically a triangle.

You can also change the style to `display: block` to remove the disclosure triangle.

See the [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/summary#browser_compatibility) section for details, as not all browsers support full functionality of this element yet.

### examples

Below are some examples showing `<summary>` in use. You can find more examples in the documentation for the [`<details>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details) element.

#### basic example

A simple example showing the use of `<summary>` in a [`<details>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details) element:

```
<details open>
  <summary>Overview</summary>
  <ol>
    <li>Cash on hand: $500.00</li>
    <li>Current invoice: $75.30</li>
    <li>Due date: 5/6/19</li>
  </ol>
</details>
```

#### summaries as headings

You can use heading elements in `<summary>`, like this:

```
<details open>
  <summary><h4>Overview</h4></summary>
  <ol>
    <li>Cash on hand: $500.00</li>
    <li>Current invoice: $75.30</li>
    <li>Due date: 5/6/19</li>
  </ol>
</details>
```

This currently has some spacing issues that could be addressed using CSS.

**Warning:** Because the `<summary>` element has a default role of [button](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/button_role) (which strips all roles from child elements), this example will not work for users of assistive technologies such as screen readers. The `<h4>` will have its role removed and thus will not be treated as a heading for these users.

#### HTML in summaries

This example adds some semantics to the `<summary>` element to indicate the label as important:

```
<details open>
  <summary><strong>Overview</strong></summary>
  <ol>
    <li>Cash on hand: $500.00</li>
    <li>Current invoice: $75.30</li>
    <li>Due date: 5/6/19</li>
  </ol>
</details>
```

## time

The **`<time>`**[HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) element represents a specific period in time. It may include the `datetime` attribute to translate dates into machine-readable format, allowing for better search engine results or custom features such as reminders.

It may represent one of the following:

- A time on a 24-hour clock.
- A precise date in the [Gregorian calendar](https://en.wikipedia.org/wiki/Gregorian_calendar "Gregorian calendar") (with optional time and timezone information).
- [A valid time duration](https://html.spec.whatwg.org/multipage/common-microsyntaxes.html#valid-duration-string).

#### datetime

This attribute indicates the time and/or date of the element and must be in one of the formats described below.

### usage notes

This element is for presenting dates and times in a machine readable format. For example, this can help a user agent offer to add an event to a user's calendar.

This element should not be used for dates prior to the introduction of the Gregorian calendar (due to complications in calculating those dates).

The _datetime value_ (the machine-readable value of the datetime) is the value of the element's `datetime` attribute, which must be in the proper format (see below). If the element does not have a `datetime` attribute, **it must not have any element descendants** , and the _datetime value_ is the element's child text content.

#### valid datetime values

a valid year string

`2011`

a valid month string

`2011-11`

a valid date string

`2011-11-18`

a valid yearless date string

`11-18`

a valid week string

`2011-W47`

a valid time string

`14:54`

`14:54:39`

`14:54:39.929`

a valid local date and time string

`2011-11-18T14:54:39.929`

`2011-11-18 14:54:39.929`

a valid global date and time string

`2011-11-18T14:54:39.929Z`

`2011-11-18T14:54:39.929-0400`

`2011-11-18T14:54:39.929-04:00`

`2011-11-18 14:54:39.929Z`

`2011-11-18 14:54:39.929-0400`

`2011-11-18 14:54:39.929-04:00`

a valid duration string

`PT4H18M3S`

### examples

#### simple example

```
<p>The concert starts at <time datetime="2018-07-07T20:00:00">20:00</time>.</p>
```

#### [`datetime`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/time#datetime_example "Permalink to datetime example") example

```
<p>The concert took place on <time
  datetime="2001-05-15T19:00">May 15</time>.</p>
```

### browser compatibility

not compatible with Internet Explorer, no solutions ave been proposed
