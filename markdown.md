# Markdown Notes

I created this Markdown guide mostly as a future reference tool for myself.

## Markdown

Markdown is a markup language that was created in 2004 by John Gruber with Aaron Swartz. It's a simple way to write content. You can use HTML and CSS with Markdown, which makes it more useful.

## Headers

To create a Header 1, use one number sign (#). To create a Header 2, use two number signs (##). As you might be able to see, the number of number signs used corresponds to the heading level. Make sure to add a space between the header name and the number signs.

```
##### Header 5 
```

You can also use the equal sign (=) and dashes (-) below the header name to make a Header 1 and a Header 2, respectively. See below for an example.

```
Header 2
-------- 
```

However, I think that it's much easier to just use number signs.

## Paragraphs

Paragraphs are very easy. All you have to do is type normally!

```
This is a sentence.
```

## Line Breaks

To create a line break, you can use the <br> tag.
```
This is the first sentence.
<br>
This is another sentence.
```
You can also skip a line (hit enter twice). If you hit enter once and go to the line below, the text is on the same line.

This is correct and will give you a line break:

```
This is the first sentence.

This is another sentence.
```

This is wrong and will not give you a line break:

```
This is the first sentence.
This is another sentence.
```

## Horizontal Rules

Horizontal rules are just lines than extend horizontally. They are very easy to create. All you have to do is have at least three dashes in a row (---).

```
Section 1
---
Section 2
```

## Emphasis

In Markdown, you can create emphasis on certain words and phrases. There are two ways to do this. You can either use Markdown or HTML tags.

To **bold** a phrase in Markdown, add either two asterisks or two underscores on both sides of the phrase. I recommend using astericks.

```
**bold**
__bold__
```
To *italicize* a phrase in Markdown, add one asterisk or one underscore to both sides of the phrase. Again, I recommend using astericks.

```
*italicize*
_italicize_
```

To ~~strikethrough~~ some text, use two tildes(\~\~) on each side on the text.

```
~~strikethrough this~~
```

Like I said earlier, you can also use HTML tags. For bold, you can use <strong></strong>. For italics, you can use <em></em>.

```
<strong>bold</strong>
<em>italics</em>
```

## Unordered Lists

The first type of list is an unordered list. Unordered lists have bullet points and no numbers that order them. All you have to do is a dash and a space. Then, you can put your content in. Don't forget the space.

```
- Eggs
- Bacon
- Muffins
```
## Ordered Lists

The other type of list is an ordered lists. As you probably guessed, ordered lists are ordered. To make it easier, you don't actually have to write all of the numbers yourself. You can just write 1. for each of them. The code doesn't show it, but the output will show the correct numbers.

```
1. Grab the ingredients.
1. Cream the sugar and the butter.
1. Beat in the eggs
```

## Quotes

To make a quote or to quote someone, all you have to do is use the greater than symbol (>) and then a space. The quotes can carry on for several lines.

> "Wait, I need to think of a quote!"
> - me, 2020

## Code

I've been using the code function of Markdown to show you code snippets. First, you can use one grave accent (\`) on each side of the code to create inline code. Also, if you ever only want one grave accent without creating inline code, use a slash (\) to override it.

```
`inline text`
```

The other way is to use three grave accents (\`\`\`) above and below the code.

```
    ```
    code
    ```
```

You can "add" and "subtract" code. See below:

```
int x=10;
- int y=1;
+ int y=11;
```
Another way to do code snippets is to use tab once or space four times.

```
    int x=10;
```
## Links

To make a link, use this format:

```
[link name](https://www.link.com "mouseover text (can be blank)")
```

You can also reuse links by doing this:

```
[link name][1]
[1]: https://www.link.com
```

## Images

Images are very similar to links. All you have to do is add an exclamation mark (!) in front.

```
![alt text](image.jpg)
```

You can style them with CSS.

## Tables

Tables aren't supported by everything. Here's an example of what one should look like in Markdown:

```
| Animal | Amount |
| :-----------: | :-----------: |
| Dog | 1000 |
| Cat | 900 |

```

The alignment of the table will change based on the placement of the colons in the second line of the table. 
For left alignment, put one colon on the left of each side (:--------). 
For center alignment, put one colon on each side of each side (:--------:).
For right alignment, put one colon on the right of each side (--------:).

## Task Lists

Task lists are fairly simple. This is the format:

```
- [x] Buy bananas
- [ ] Go to the movies
- [ ] Read a book
```

Make sure you keep the space between the dash (-) and the square brackets ([ ]). Also, make sure there's a space between the brackets if there's no x.

## Footnotes

Footnotes kind of look like the way to reuse links ([1]). See below:

```
Look, it's a footnote! [^1]

[^1]: This is a footnote.
```

## Emojis

You can use emojis in Markdown by using emoji codes. Remember that different Markdown processors may have different codes.

```
:smiley:
```

In Github, the above emoji code should be for a smiley face.

## Resources

[Mastering Markdown](https://masteringmarkdown.com/)

This free course is by Wes Bos. It is less than one hour long.

[Markdown Guide](https://www.markdownguide.org/)

This is a guide that contains everything there is to know about Markdown.

[Dillinger](https://dillinger.io/)

This is a website that you can use to look at your Markdown.
