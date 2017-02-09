# gen-epub-book.awk [![TravisCI Build Status](https://travis-ci.org/nabijaczleweli/gen-epub-book)](https://travis-ci.org/nabijaczleweli/gen-epub-book) [![AppVeyorCI build status](https://ci.appveyor.com/api/projects/status/197cavyvmq0vn2gr/branch/master?svg=true)](https://ci.appveyor.com/project/nabijaczleweli/gen-epub-book/branch/master) [![Licence](https://img.shields.io/badge/license-MIT-blue.svg?style=flat)](LICENSE)
Generate an ePub book from a simple plaintext descriptor.

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
  awk gen-epub-book.awk -v temp="$TEMP > out/test.epub"
```

For more detailed usage information and tag list, see the [manpage](https://cdn.rawgit.com/nabijaczleweli/gen-epub-book/man/gen-epub-book.awk.1.html).

## Why?

There really are no good alternatives and I wanted soemthing automated to be able to deploy this to a
[webpage](https://nabijaczleweli.xyz/capitalism/writing_prompts) so I could download stuff to my Kindle.

Also, why not?

## [Previous history](https://github.com/nabijaczleweli/nabijaczleweli.github.io/commits/dev/gen-epub-book.awk)

## Versions in other languages

Currently none. Come back later.
