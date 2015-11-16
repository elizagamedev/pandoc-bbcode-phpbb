[link:pandoc]: <http://johnmacfarlane.net/pandoc/README.html>
[link:pandoc-bbcode]: <https://github.com/2ion/pandoc-bbcode>
[link:pandoc-bbcode-phpbb]: <https://github.com/anshumanb/pandoc-bbcode-phpbb>

# pandoc-bbcode-phpbb

## Introduction

This is a modified Lua script to write phpBB's subset of BBCode via
[pandoc][link:pandoc] based on the [original pandoc-bbcode][link:pandoc-bbcode]
and [pandoc-bbcode-phpbb][link:pandoc-bbcode-phpbb]. The aim is to be able to
output BBCode as perfectly formatted as possible with the result not necessarily
being human-readable.

This script can be used used with Pandoc in the following way:

    pandoc -t pandoc-bbcode-phpbb.lua -o $output $input

## Markdown Demonstration

### Sectioning

# First level header
## Second level header
### Third level and other headers

### Text emphasis

_Simple emphasis_, __strong emphasis__

### Quoting

Quotes without attribution:

> This is a quotation with no author specified.

Quotes with attribution:

> @Username: This text was written by "Username"

Though not standard in phpBB, you can also use `@spoiler` to generate a spoiler
block:

> @spoiler
> It was Earth all along!

### Footnotes

We can now do footnotes[^1]. They will be put at the very end of the
post!

[^1]: You see, this is how footnotes work! But BBCode still sucks.

### Links and images

[Check out this amazing website.](www.zombo.com)

![This alt text isn't used in BBCode, unfortunately.](http://i.imgur.com/B63RuQLl.jpg)

### Lists

Simple, simple, and without using the sick BBCode syntax!

* Spam
* Spam
    1. Eggs
    2. Sausage
    3. Spam
* Spam
    1. Cheese
* Baked beans
* Spam

### Tables

BBCode doesn't render tables, nor allows it raw HTML tags. The only
solution for rendering thus is rendering them as ASCII tables, but it gets the
job done.

| Heading 1 | Heading 2        | Heading 3 |
| --------- |:----------------:| ---------:|
| left      | centered         |     right |
| groovy    | this is text     |   radical |
| Unicod€   | Slagsmålsklubben |    Piñata |

within `[code]` tags.

### Horizontal Rule

Above

-----

Below

### Miscellaneous Features

These features either aren't part of standard installations of phpBB or have
no 1:1 implementation otherwise.

* ~~Strikethrough~~ text
* `inline code`
