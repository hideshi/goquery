# goquery - a little like that j-thing, only in Go

GoQuery brings a syntax and features similar to [jQuery][] to the [Go language][go]. It is based on the [experimental html package][exphtml] and the CSS Selector library [cascadia][]. Since the html parser returns tokens (nodes), and not a full-featured DOM object, jQuery's manipulation and modification functions have been left off (no point in modifying data in the parsed tree of the HTML, it has no effect - although it could be used to re-render the HTML from a modified node tree afterwards... maybe someday).

Supported functions are (will be) query-oriented features (`hasClass()`, `attr()` and the likes), as well as traversing functions that make sense given what we have to work with. This makes GoQuery a great library for scraping web pages.

Syntax-wise, it is as close as possible to jQuery, with the same function names when possible, and that warm and fuzzy chainable interface. jQuery being the ultra-popular library that it is, I felt that writing a similar HTML-manipulating library was better to follow its API than to start anew (in the same spirit as Go's `fmt` package), even though some of its methods are less than intuitive (looking at you, [index()][index]...).

## Installation

Since this library (and cascadia) depends on the experimental branch, this package must be installed first. Both GoQuery and Cascadia expect to find the experimental library with the `"exp/html"` import statement. To install it at this location, please [follow this guide][wikiexp].

Once this is done, install GoQuery:

`go get github.com/PuerkitoBio/goquery`

## API

GoQuery exposes two classes, `Document` and `Selection`. Unlike jQuery, which is loaded as part of a DOM document, and thus acts on its containing document, GoQuery doesn't know which HTML document to act upon. So it needs to be told, and that's what the `Document` class is for. It holds the root document node to manipulate, and can make selections on this document.

Please note that Cascadia's selectors do NOT necessarily match all supported selectors of jQuery (Sizzle). See the [cascadia project][cascadia] for details.

GoQuery's complete [godoc reference documentation can be found here][doc].

## Examples

Coming soon...

## License

The [BSD 3-Clause license][bsd], the same as the [Go language][golic]. Cascadia's license is [here][caslic].

[jquery]: http://jquery.com/
[go]: http://golang.org/
[exphtml]: http://code.google.com/p/go/source/browse#hg%2Fsrc%2Fpkg%2Fexp
[cascadia]: http://code.google.com/p/cascadia/
[wikiexp]: http://code.google.com/p/go-wiki/wiki/InstallingExp
[bsd]: http://opensource.org/licenses/BSD-3-Clause
[golic]: http://golang.org/LICENSE
[caslic]: http://code.google.com/p/cascadia/source/browse/LICENSE
[doc]: http://go.pkgdoc.org/github.com/puerkitobio/goquery
[index]: http://api.jquery.com/index/
