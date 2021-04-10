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

The cite attribute, when paired with `<blockquote>` or `<q>`, is particularly important when used with the WHATWG methodology of quoting, where the person who said it or the work are not included within the `<blockquote>` or `<q>` element. The *cite* attribute would therefore connect the URL reference to the thing that was said, since no other method is possible with their rules.

But again, we are open to instruction from anyone who can explain this more clearly than we can.

# `<dfn>`

`<dfn>` is used to indicate the term being defined within the context of a definition phrase or sentence.

That means we'll look to the nearest or surrounding `<p>`, `<dd>` within a definition list (tomorrow!), or `<section>` element (Day 18) for the definition of the term.

### Ways to use `<dfn>`
The most obvious usage is to indicate the term being described within the context of the phrase or sentence. Here, "Godzilla" is defined by the rest of the paragraph.

    <p>My son thinks he is <dfn>Godzilla</dfn>, who is generally depicted as an enormous, violent, prehistoric sea monster awakened and empowered by nuclear radiation. It's true, there are similarities.</p> 

If we mention the definition again later in our content, we can add a bookmark link to jump back to the term nearest to the definition.

    <p>He is not as enamored with <dfn id="kong">King Kong</dfn> who resembles an enormous gorilla-like ape that has appeared in various media since 1933. </p> 
    
    ...
    
    <p>Complaints about <a href="#kong">Kong</a> include how he has no atomic fire breath.</p> 
One common -- and useful -- combination is to pair `<dfn>` with `<abbr>` (the abbreviation tag, appearing in an email near you on day 7) in order to define a term along with an acronym.

    <p><dfn><abbr title="Massive Unidentified Terrestrial Organism">MUTO</abbr></dfn> refers to a species of giant monsters that first appeared in <cite>Godzilla</cite> (2014) and <cite>Godzilla: King of the Monsters</cite> (2019). In <cite>Godzilla vs. Kong</cite> (2021), the enemy has changed.</p> 

###Little known facts about `<dfn>`
Both MDN and WHATWG say that if `<dfn>` has a title attribute, the attribute MUST contain only the term and no other text. Our thought is that this could be for a nickname, rather than an abbreviation, otherwise, it's unclear in the documentation what the difference is!

    <p>In the Godzilla-verse, <dfn title="Ghidorah">Monster Zero</dfn> is a giant extraterrestrial three-headed dragon-like monster.</p> 
If you are using a `<dl>` (Day 5, tomorrow!) as a DEFINITION list, then it's acceptable and perhaps even desirable to double tag the term with `<dfn>`. (Spoiler alert: `<dl>` may also be a description list!)

    <dl>
       <dt><dfn>Monster Island</dfn></dt>
       <dd>Island where Godzilla lives</dd>
       <dt><dfn>Skull Island</dfn></dt>
       <dd>Island where Kong lives</dd>
    </dl>
###Common attributes
Common attributes include *title* and *id*, as explained earlier.

# Description lists and `<dl>`, `<dt>`, `<dd>`

Today we focus on the three elements that make up a description list, historically called the definition list: `<dl>`, `<dt>`, and `<dd>`.

While ordered `<ol>` and unordered `<ul>` lists are made of a series of **single items**, a description list has **pairs of information**. If there is a RELATIONSHIP between the term and the details, then you can technically use a description list.

The meaning of each tag is as follows:

- `<dl>` description list (or definition list)
- `<dt>` description name (or definition term)
- `<dd>` description details (or definition)

(*The above would be best marked up with a definition list. Unfortunately, we cannot access the Substack code to make it so. Yep, we’re as guilty of bad markup as anyone else.*)

Typically, a description list might be used with many types of information:

- 📚 Author and book title(s)
- 📷 Location and photographer
- 🕸 Website and description
- 🎪 Date and event
- ❓(Frequently Asked) Question and answer

You might also use it for some specific metadata at the start of an article or a recipe.

### Examples of a description list
A more general use is as a description list. Here we have two stores and things to purchase at each one:

    <dl>
       <dt>Target</dt>
         <dd>dish soap</dd>
         <dd>socks</dd>
       <dt>Fresh Thyme</dt>
         <dd>coconut water</dd>
         <dd>strawberries</dd>
         <dd>aged gouda</dd>
    </dl> 

The classic use as a definition list consisting of terms and definitions still works. It's lovely. Don't forget to include the <dfn> tag as appropriate!:

    <dl>
       <dt><dfn>Target</dfn></dt>
       <dd>Chain of stores selling clothing, electronics, health supplies and general household items</dd>
       <dt><dfn>Fresh Thyme</dfn></dt>
       <dd>A Midwestern grocery store chain in the United States</dd> 
    </dl> 
###Duplicating terms and descriptions
As shown above, you may have more than one `<dt>` for a `<dd>`, and you may have more than one `<dd>` for a `<dt>`.

If you have multiple `<dt>` elements in a row, it's assumed these are all names for the same thing.

If you have multiple `<dd>` elements in a row, it's assumed these are all possible descriptions for the term(s) immediately preceding the description.


###Little known fact about description lists
WHATWG is permitting `<div>` elements inside of `<dl>` now for two purposes: styling and for holding microdata elements. 

    <h3>Grandma's Apple Pie</h3>
     <dl>
       <div>
         <dt>Preparation time</dt>
         <dd>1 hour</dd>
       </div>
       <div>
         <dt>Baking time</dt>
         <dd>45 minutes</dd>
       </div>
       <div>
         <dt>Oven temperature</dt>
         <dd>350 degrees</dd>
       </div>
     </dl>
