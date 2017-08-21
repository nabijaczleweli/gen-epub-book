# [gen-epub-book](https://nabijaczleweli.xyz/content/gen-epub-book).awk [![TravisCI Build Status](https://travis-ci.org/nabijaczleweli/gen-epub-book.svg?branch=master)](https://travis-ci.org/nabijaczleweli/gen-epub-book) [![AppVeyorCI build status](https://ci.appveyor.com/api/projects/status/197cavyvmq0vn2gr/branch/master?svg=true)](https://ci.appveyor.com/project/nabijaczleweli/gen-epub-book/branch/master) [![Licence](https://img.shields.io/badge/license-MIT-blue.svg?style=flat)](LICENSE)
Generate an ePub book from a simple plaintext descriptor.

## [Webpage](https://nabijaczleweli.xyz/content/gen-epub-book)

## [Manpage](https://cdn.rawgit.com/nabijaczleweli/gen-epub-book/man/gen-epub-book.awk.1.html)

## Quickstart

Copy this somewhere:

```
Name: Simple ePub demonstration
Cover: cover.png

Image-Content: simple/chapter_image.png
Content: simple/ctnt.html

Author: nabijaczleweli
Date: 2017-02-08T15:30:18+01:00
Language: en-GB
```

Modify to your liking, then, assuming you put the file in "example/test.epupp" and want to write the result to "out/test.epub", run:

```sh
echo -e "Self: example/test.epupp\nOut: out/test.epub" | cat - example/test.epupp | \
  awk gen-epub-book.awk -v temp="$TEMP
```

For more detailed usage information and tag list, see the [manpage](https://cdn.rawgit.com/nabijaczleweli/gen-epub-book/man/gen-epub-book.awk.1.html).

## AWK support

AWK version|Supported
-----------|---------
GAWK       | :+1:
MAWK       | :-1:

Other versions untested, open an issue if you want one.

## Dependencies

A supported AWK version, obviously. The built-in should suffice on Linux, but `gawk` on APT and MSYS2 will work.

Info-ZIP, a.k.a. `zip` on both APT and MSYS2.

If you want to build the examples, you need [Calibre](https://calibre-ebook.com).

## Why?

There really are no good alternatives and I wanted soemthing automated to be able to deploy this to a
[webpage](https://nabijaczleweli.xyz/capitalism/writing_prompts) so I could download stuff to my Kindle.

Also, why not?

## [Previous history](https://github.com/nabijaczleweli/nabijaczleweli.github.io/commits/dev/gen-epub-book.awk)

## Versions in other languages

A rewrite in [Rust](https://github.com/nabijaczleweli/gen-epub-book.rs).

A rewrite in [C++](https://github.com/nabijaczleweli/gen-epub-book.cpp).

A rewrite in [Scala](https://github.com/nabijaczleweli/gen-epub-book.scala).
