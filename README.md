# litterarum

Think devops but not ops, _docs_.

In his blog article,
[six languages to master](https://michaelochurch.wordpress.com/2012/07/27/six-languages-to-master/),
Michael O'Church makes compelling argument for developers to write
documentation.

> One of the biggest errors I encounter with regard to commenting is the
  tendency to comment minutiae while ignoring the big picture.

To see the big picture sometimes you need to step away from the code
altogether and describe the design and architecture of what you have
written. We shouldn't confuse this with speculative _upfront_
documentation which is rarely possible to implement precisely. But
_accurately documenting how a working system works can help others
understand it_.

## Plain-text wins

For writing good prose you just can't beat plain-text. Many have
tried, but plain-text just won't die. Years ago many business people
were writing documents in word-processing products like Microsoft
Word. But as soon as e-mail arrived, plain-text took over.

That's why this documentation systems prefers _Markdown-formatted
text_. 

[Markdown](http://daringfireball.net/projects/markdown/) provides just
the right level of features (text-decoration, nested section headings,
hyperlinks) without requiring a specialist program to create it. Anyone
who has written a simple e-mail will be familiar with Markdown, or
almost. This fact makes it easy to capture good content - you can even
get your boss to write documentation - by distilling content out of
e-mails (using a technique called 'copy-and-paste').

Even better, since Markdown has been popularized by sites like GitHub
and StackOverflow, many people both technical and non-technical are already
familiar with the format.

So it's Markdown, let's move on.

## HTML, PDF and ebook outputs

HTML seems to be the way things are heading for documentation but
sometimes PDF is a good option for distributing documentation to others
quickly, survives web server outages and can look great.

Litterarum will also support other formats such as ebooks.

## Document publication

This repository contains instructions for creating a working publication
system for developer documentation based on standards by integrating a
mature set of commonly available tools.

I believe that good documentation combines good writing with a degree of
engineering behind the publication system. Monolithic documentation
tools such as Microsoft Office remove the need for this engineering
requirement but do so by making trade offs I'm unwilling to accept.

Here follows the long list of the ingredients you will need. Some are
optional but I recommend installing everything. You don't need to know
these tools to use them.

## Required components

Doug McIlroy writes about the [Unix Philosophy](http://en.wikipedia.org/wiki/Unix_philosophy#McIlroy:_A_Quarter_Century_of_Unix) :-

> Write programs that do one thing and do it well. Write programs to work together. Write programs to handle text streams, because that is a universal interface.

### GNU Make

Make is a great tool. Especially for producing documentation pipelines. 

### sed

sed makes a handy text-replacement tool, perfect for variable
substitution in text.

### Pandoc

[Pandoc](http://johnmacfarlane.net/pandoc/) reads Markdown text and
produces DocBook XML.

### DocBook

DocBook is the gold-standard of documentation formats and is used by
organisations such as O'Reilly and RedHat.

DocBook originated as an SGML authoring format. The XML version took a
few years to mature but is now stable enough to build a foundation
on. While DocBook has a significant number of features, it's still a
painful and error-prone to author text in XML without a specialist tool.

This system supports Markdown as the primary input format and converts this to DocBook XML. This sections and chapters to be provided in native DocBook XML where appropriate.

### XSLT

An XSLT processor can transform XML inputs to XML outputs.

### dblatex

You need to watch out that you install version 3.3. On my system (Fedora 17) there's only 3.0 available and you'll need a simple patch to fix it.

## Optional components

These aren't strictly required but I highly recommend that you don't
stop here - if you've come this far then it's well worth carrying on to
completion.

### roqet

I like to define all system and application configuration in RDF. You
can use other formats such as XML and JSON but RDF brings some formality
to the procedings - on a very large system this can help. RDF also has
strong support for self-documentation, which accords with our litterarum
values. But you can use JSON too.

## inkscape

Inkscape can be used to create drawings for diagrams in your documentation, but I don't recommend it. It's a bit primitive as a diagram editor and there are better alternatives (such as diagram.ly below). However, inkscape is a requirement because it is used by dblatex (in headless mode) for converting between SVG and PDF.

## [diagram.ly](http://diagram.ly)

This is a web based tool that helps create diagrams - save these as [SVG](http://en.wikipedia.org/wiki/Scalable_Vector_Graphics).

## dot

[Dot](http://en.wikipedia.org/wiki/DOT_language) is a great tool for
quickly generating diagrams, particularly those based on simple graphs
(dependencies, data-flows, etc.)

## GNU/Linux

This system is based on some of the oldest and most mature tools
available which were created decades ago and perfected on the Unix
system. For this reason many of the components listed here can already
be found pre-installed on a GNU/Linux distribution and not difficult to
set up on OS X.

You might even be able to get these components working on Windows, but
the installation and integration will be a _lot_ harder. Microsoft still
want you to use Office to write your documents. There is also a much
bigger market for commercial tools on Windows to fill this gap. If you
want to use this system but have to use Windows I highly recommend
installing a Linux distribution as a [virtual host](https://www.virtualbox.org/).

## How to put the system together

How do we know where to put everything?

Follow the conventions in this repository and all should be well.

# Are we there yet?

I have just got this README up. Over the next few weeks I'll be adding the Makefile to create a PDF from it.
