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

# `<details>` and `<summary>`

`<details>` is a wrapper for a `<summary>` sentence or term and its longer explanation that begins collapsed. By clicking on a triangle next to the summary, we reveal a longer explanation.

🪗 It's the EASIEST WAY TO MAKE AN ACCORDION MENU! 🪗

True, animation effects to smooth out the transition are not available, but in a pinch, we think you'll find you love this tag as much as we do! 💕

###Example
The details/summary combination is perfect for information similar to a definition list, but which might have a series of items that stand alone, rather than grouped in list format:

    <details>
       <summary>Reading the fine print</summary>
       <p>This is where we hide all of the secret terms and conditions. Your mileage may vary.</p> 
    </details> 
The `<summary>` element is optional. Without it, you'll get the default clickable text which says "details." The `<summary>` element must also be the first child of `<details>`. Include it as the very first thing inside the `<details>` element.

### Little known facts about `<details>` and `<summary>`
 - ⛔️ The details element is not appropriate for footnotes. Seems like it would be a great fit, but unfortunately, it's not. See WHATWG for more information.

- ⛔️ There is currently no way to control the animation between the summary being hidden and revealed.

- ✅ The `<summary>` element is used nowhere else in HTML. It may only be used with `<details>` and only as a first-child of `<details>`. How's that for a specific element?

###Common attributes
By including the open attribute in the `<details>` element, the element will appear open by default on the page, rather than closed:

    <details open>
       <summary>About My Life</summary>
       <p>My life is as open as this details panel.</p> </details> 
When a summary is opened, an open attribute is added to details. This attribute may be used to style each state. [The below example is from WHATWG](https://html.spec.whatwg.org/multipage/interactive-elements.html#the-details-element):

    details > summary {
    transition: color 1s;
    color: black;  
    }
    details[open] > summary {
    color: red;  
    }

# `<abbr>`

**TLA: three-letter acronym.*

`<abbr>` is for abbreviations or acronyms. If you're using them in your writing, well, you should define them. Your teacher told you this in school, and we're telling you again for your HTML.

### How `<abbr>` works
A good web starts with well-written content. Erika and Jen speak English in the United States, and this is our bias in the below advice. Modify the below advice to fit with grammar rules and conventions for your language and country.

✅ If you learned to write papers in the US, you know that the first time you use an acronym or abbreviation, you should define it, unless it's extremely well known.

    <p>We are excited to see where NASA takes us next, given their many successes on the Moon and Mars.</p> 
To a US-based audience, we are so familiar with NASA, we may not know exactly what NASA stands for (or care, to be honest). However, it is an acronym, and we can mark it up as such:

    <p>We are excited to see where <abbr>NASA</abbr> takes us next, given their many successes on the Moon and Mars.</p> 
Yeah, not super helpful. We already guessed it was an abbreviation or acronym of some kind, but we still don't know what it stands for.

✅ If you want to communicate the words behind the NASA acronym, there are two possibilities. We like this methodology, which combines good English writing practices with HTML:

    <p>We are excited to see where the <dfn id="NASA">National Aeronautics and Space Administration</dfn> (<abbr title="National Aeronautics and Space Administration">NASA</abbr>) takes us next, given their many successes on the Moon and Mars.</p> 
See how we combine `<dfn>`, which defines the abbreviation, with `<abbr>`? The ID in `<dfn>` may be used to link to that definition later in the document. (See Day 4 for details.)

The title attribute in `<abbr>` also tells us what the NASA acronym means, but the meaning is hidden. You may have seen this show up as a dotted line in some browsers, with a tooltip that appears when one hovers over the link. That's nice, but now one must do some work to see what the abbreviation means, rather than reading it in the sentence. Also, what happens if you're on a device that doesn't hover? That situation is nicely addressed above through content and markup.

However, if you're working with an abbreviation or acronym that is well-known, and not many people might need help with knowing what this is, you may leave the definition in the title attribute for the `<abbr>` element.**

    <p>We are excited to see where <abbr title="National Aeronautics and Space Administration">NASA</abbr> takes us next, given their many successes on the Moon and Mars.</p>  
***Many of Jen’s current and former students now hear her voice in their heads: “Just because you can doesn’t mean you should…”*

##Common misconceptions

###Deprecated `<acronym>` element
⛔️ Older HTML specifications included a separate <acronym> element, which is now deprecated. While there is a difference between acronyms and abbreviations, developers aren't that picky about the *semantic* difference.

###Differences in display across browsers
⛔️ Some of these older browsers (IE in particular) don't style `<abbr>` the same way that our favorite browsers do (a dotted underline plus tooltip). As always, check across browsers for consistency in styling.

###Don't go crazy with `<abbr>`
✅ Even the specifications state that not every instance of an abbreviation or acronym requires an `<abbr>` tag. Consider that Dr. is an abbreviation for "doctor" - would you seriously mark that up every time it occurs in medical documentation? We think not. Apply `<abbr>` judiciously. Don't go bananas.

###Commonly used attributes
We described the title attribute in detail earlier:

    <abbr title="National Aeronautics and Space Administration">NASA</abbr>
The title attribute, when associated with the `<abbr>` element, must contain the definition of the acronym or abbreviation and nothing else.

### [`<abbr>` demo](https://codepen.io/jen4web/pen/XWpaqmm?editors=1100)

# `<small>`

Read the Fine Print. It's become an art form in American society. Legal disclaimers, copyright notices, terms and conditions, privacy notifications, and so much more. It's all of those sticky details that must be disclosed, but companies like to keep hidden.

Those disclaimers and details are printed in tiny type to minimize printing costs and discourage detailed reading. We can do the same on the web!

### A brief history of `<small>`
Back in the Dark Days Before CSS, `<small>` was used for... small text! As in, text that's not big. That was for the `<big>` element, of course.

⛔️ Then we got wise, separated presentation from markup, and `<small>` was tossed in the great 😠 *Dustbin of Frowned-Upon Elements* 😠 for several years during HTML4 and XHTML 1.0.

✅ HTML5 brought back `<small>` with its new meaning, while it deprecated `<big>`. In the new definition, `<small>` is the fine print. As [MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/small) says, copyright, legal text, and side-comments are all candidates for `<small>`.

### When to use `<small>`
✅ If it's a brief passage of "fine print," as an exception to the rest of the page's content, `<small>` is a great choice.

    <p><small>&copy; 2021 by me. All rights reserved, baby.</small></p> 
⛔️ If it's an extended passage of fine print, like the pages containing the full privacy policy, terms and conditions, or other disclaimers of use, don't repeat `<small>` over and over again. On those pages, the fine print is the focus of the page, not the exception to it.

✅ `<small>` may also be used to indicate limitations on an offer.

    <p>Today only: $10 off your purchase! <small>must purchase $1000 or more</small></p> 
###Common misconceptions about `<small>`
⛔️ WHATWG cautions against using `<small>` as the "opposite" of strongly emphasized (`<strong>`) or emphasized (`<em>`) text:

The small element does not "de-emphasize" or lower the importance of text emphasized by the em element or marked as important with the strong element. To mark text as not emphasized or important, simply do not mark it up with the em or strong elements respectively.

👀⚠️ Finally, always ask yourself if you're using `<small>` for styling or if you're using it to convey specific meaning. If it's styling, use CSS. 👀 ⚠️

###[A `<small>` demo](https://codepen.io/jen4web/pen/OJWjomB)

# `<wbr>` and &shy

As developers, we tend to ignore some of the nice styles that print designers have tweaked in their work for years. For example, we don’t often modify kerning, leading, widow/orphan control, or hyphenation in our sites. Nor do we tend to think much about a paragraph of information that wraps onto multiple lines. Where exactly are the line breaks occurring? How do we make the rag look even?

*[8 Simple Typography Tips For Your Designs from Smashing Magazine](https://www.smashingmagazine.com/2009/04/8-simple-ways-to-improve-typography-in-your-designs/)*

But the designers among us will be super happy to know that we have some control over the rag using `<wbr>`, the word break tag, and `&shy;`, the "shy" hyphen.

###What does `<wbr>` do?
Long words don't automatically hyphenate on the web. What's more, for developers trying to make text look good on the range of screen sizes we support, inevitably marketing and/or the designers will find that ONE ANNOYING SCREEN where it looks bad and harp on it endlessly. Not that we have ever personally experienced this.

    <p>Somewhere out there, on some screen, this sentence will look awful because of <dfn>sesquipedalianism</dfn>, a love of long words.</p> 
We suppose you could do some JavaScript magic to address this problem. But you know what's coming next. The content writers complain that the hyphens are in the wr-on-g spot.

<wbr> performs an essential public service in indicating where word breaks might occur as set by a human.

    <p>Somewhere out there, on some screen, this sentence will look awful because of <dfn>ses<wbr>qui<wbr>pe<wbr>dal<wbr>ian<wbr>ism</dfn>, a love of long words.</p> 
*(We may have over-<wbr>-ed in this example.)*

✅ This breaks up sesquipedalianism in the right spots, and the breaks appear only if needed. See the [CodePen demo](https://codepen.io/jen4web/pen/bGgYERj) for <wbr> in action.

⛔️ The next problem is "BUT WAIT THERE IS NO HYPHEN." Correct. `<wbr>` does not provide you with a hyphen. This may be helpful for those occasions where a break is needed but a hyphen is not desired.

For example, have you ever styled a long URL on a page? (University peeps: citations, amirite?) `<wbr>` handles this well without adding extra characters. See the [CSS Tricks article](https://css-tricks.com/better-line-breaks-for-long-urls/) that will walk you through this.

###What does `&shy;` do?
✅ You guessed it already! A "shy" hyphen is a hyphen that appears only when needed.

    <p>Somewhere out there, on some screen, this sentence will look awful because of <dfn>ses&shy;qui&shy;pe&shy;dal&shy;ian&shy;ism</dfn>, a love of long words.</p> 

### CSS-based typography properties
HTML is for markup, so there's not much else we can do with `<wbr>` and `&shy;` in #30DaysofHTML.

However, there are many well-supported CSS properties that also control other aspects of typography. It's more than Google Fonts.

What's more, if browsers don't support these CSS properties, you are no worse off than you would be if you didn't include them. That's progressive enhancement at its finest!

- Widow/orphan control (Firefox doesn't support widows and orphans. Ponder that for a minute, you monsters.)

- CSS hyphenation (works great for English, not so great in other languages)

- CSS columns to shorten line lengths for improved reading

- CSS word breaks to prevent words from overflowing their container

- [Type scales](https://type-scale.com/) for well-proportioned type

And others!

###[`<wbr>` and `&shy;` demo](https://codepen.io/jen4web/pen/bGgYERj)
