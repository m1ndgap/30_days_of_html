#`<address>`

###What does `<address>` do?
`<address>` should be used for addresses. You guessed that already. But what kind of addresses, and in what context?

Address context
`<address>` was originally used to indicate contact information for the page owner. It has since evolved to include any type of contact information, generally the address of an article author or the address of a website.

- 🔹 If `<address>` is placed within an `<article>`, it is assumed this is the article author's address.

- 🔸 If `<address>` is placed closest to the `<body>` tag, it's assumed to be the website organization's address. Usually this type of information is found in a page `<header>` or   `<footer>`.

### Kinds of addresses

✅ Any information that's used to contact the website organization or the article author is fair game. That might include:

- email addresses

- social media links

- phone numbers

The contact person's name may also be included in an address element.

⛔️ However, non-contact information is to be avoided.


#`<blockquote>` and `<q>`

`<blockquote>` is for block-level quotes, while `<q>` is used for inline quotes. Optionally, these may be paired with either a <cite> element or a cite attribute. (We'll cover <cite> and cite tomorrow, Day 3.)

In other words, a longer quote goes in a `<blockquote>` element, while `<q>` marks shorter passages.

👀 Sounds easy, but it's not as straightforward as you think.

###When to use `<blockquote>`
 - ✅ You're quoting an extended passage from a book, article, website, or some other work. By making this passage stand alone, it's clear that this is something you are quoting, not something that you originally wrote.

- ✅ You're quoting what someone said as a report, not as a conversation.

- ✅ Somewhere, there's a citation that could go with this.

###When to use `<q>`
🏁 You're quoting a short passage from a book, article, website, or another work. Typically this is a few words or a line or two. Anything longer should probably use `<blockquote>`.

🏁 It's not a conversation.

🏁 There's a citation that could go with it.

###When not to use `<blockquote>` or `<q>`
- ⛔️ Dialog - if it's a conversation, it's not a quote.

- ⛔️ Sarcasm or "air quotes" - there is a double quote key on your keyboard for these. It's not just for "code."

❌ ❌ ❌ PLEASE do not use `<blockquote>` for indents. CSS is made for indents. Use it.

- ⛔️ Likewise, do not use `<q>` in particular for conversations. It has built-in curly quotes before and after your quotation. They're pretty and tempting. But they are not for your conversation.

- ⛔️ Did I mention that `<q>` is not for conversations?

###Common attributes
👀 `<cite>` and the cite attribute are commonly associated with these elements, for obvious reasons. Your original thoughts or writing are not included in `<blockquote>` and `<q>`. Therefore, a citation is appropriate. (We'll cover `<cite>` and cite tomorrow, Day 3.)


# `<cite>`

`<cite>` is for the title of a work, which can be quoted, referenced in detail, or mentioned in passing. "Works" are books, songs, paintings, programs, TV shows, operas, social media posts, and so much more. If you're referring to something that's not your own, you need to cite it in some way.

How hard could this be? So hard. WHATWG and MDN don't agree on many points, leaving we poor developers in a world of hurt. Let's start where they do agree.

### Titles of works
If it's a creative work, like the title of a book, movie, or exhibition, or the name of an opera, painting, or TV show, use `<cite>` to indicate it as such.

    <p>Baby Yoda in <cite>The Mandalorian</cite> is the cutest thing ever!</p> 

🎓 So... not exactly an academic citation, is it? We aren't linking to Disney+, or a website, or any study that has conclusively proved this statement to be true, even though we know it is true.

###Where it gets hard
Let's say we want to properly quote this:

- Who said it: The Client

- TV show: *The Mandalorian*

- Quote: "**Bounty hunting is a complicated profession.**"

- Website source: https://www.starwars.com/news/the-mandalorian-quotes

It's a short quote, so it could be inside of a `<q>` element as part of a sentence, or it could be set off as a more prominent quote in a `<blockquote>` element. Let's demonstrate the `<blockquote>` variation according to WHATWG and MDN.

###WHATWG Example 1
    <blockquote cite="https://www.starwars.com/news/the-mandalorian-quotes">  
       <p>Bounty hunting is a complicated profession.</p> </blockquote> 
    <p>The Client in <cite>The Mandalorian</cite></p> 
WHATWG maintains that the citation should not show up inside of the `<blockquote>`. It should be placed after it. The URL citation is placed as an attribute to `<blockquote>` to associate the URL with the quote.

###WHATWG Example 2
    <figure>
       <blockquote cite="https://www.starwars.com/news/the-mandalorian-quotes">
         <p>Bounty hunting is a complicated profession.</p>
       </blockquote>
       <figcaption>The Client in <cite>The Mandalorian</cite></figcaption> 
    </figure> 
This methodology associates the quote with who said it from where more strongly. (We'll talk about `<figure>` as part of the Multimedia Extravaganza toward the end of this month.)

By the way, if you feel like both of these examples make no sense, we sympathize. We are reporting their rules, not our agreement with them.

###MDN Example
    <blockquote>
       <p>Bounty hunting is a complicated profession.</p>
       <footer>The Client in <cite><a href="https://www.starwars.com/news/the-mandalorian-quotes">The Mandalorian</a></cite></footer> 
    </blockquote> 
This might be closer to what you've seen others do before. Here the character who said it and the creative work are referenced inside the `<blockquote>`. The URL is in a clickable link, although it could be referenced via the cite attribute if a clickable link was not desired for some reason.

###Common attributes
Cite may also be an attribute within:

`<blockquote>` and `<q>` (discussed in Day 2)

`<del>` and `<ins>` (discussed in Day 12)

The value for the cite attribute is only a URL reference. It's not flexible about its content as the `<cite>` element is.
