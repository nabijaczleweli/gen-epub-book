gen-epub-book.awk(1) -- Generate an ePub book from a simple plaintext descriptor
================================================================================

## SYNOPSIS

`gen-epub-book.awk -v temp`

`[ng]?awk -f gen-epub-book.awk -v temp`

## DESCRIPTION

Generate an ePub book from a simple plaintext descriptor.

## USAGE

The script requires the user to pass a temporary directory via the `temp`
variable. The systems temporary directory can be found in the `$TEMP` or
`$TMP` environment variables.

Assuming the former, the full argument will be `-v temp="$TEMP"`.

## DESCRIPTOR FORMAT

The descriptor consists of multiple lines in the format *"Key: Value"*, unknown
keys are ignored, lines that don't match the format are ignored.

  Self

    Required: yes
    Type: file path
    Value: path to file used as descriptor
    Use: to extract base directory for relative content paths
    Amount: 1
    Order: before any content

  Out

    Required: yes
    Type: file path
    Value: path to the output file
    Use: to extract temporary directory name for assembly
    Amount: 1
    Order: before any content

  Name

    Required: yes
    Type: plaintext
    Value: e-book's title
    Amount: 1
    Order: irrelevant

  Content

    Required: no
    Type: file path
    Value: relative path to (X)HTML chunk
    Amount: any
    Order: after Self
    Remarks: see ADDITIONAL CONTENT PROCESSING

  String-Content

    Required: no
    Type: (X)HTML
    Value: (X)HTML string
    Amount: any
    Order: after Self and Out

  Image-Content

    Required: no
    Type: file path
    Value: relative path to image to include in e-book
    Amount: any
    Order: after Self and Out

  Network-Image-Content

    Required: no
    Type: file URL
    Value: URL of image to include in e-book
    Amount: any
    Order: after Self and Out

  Cover

    Required: no
    Type: file path
    Value: relative path to image to use as e-book cover
    Amount: 0-1
    Order: after Self and Out
    Remarks: exclusive with Network-Cover

  Network-Cover

    Required: no
    Type: file URL
    Value: URL to image to use as e-book cover
    Amount: 0-1
    Order: after Self and Out
    Remarks: exclusive with Cover

  Author

    Required: yes
    Type: plaintext string
    Value: e-book's author
    Amount: 1
    Order: irrelevant

  Date

    Required: yes
    Type: ISO-8601-compliant date
    Value: e-book's authoring/publishing date
    Amount: 1
    Order: irrelevant

  Language

    Required: yes
    Type: ISO-639-1-compliant language code
    Value: language used in e-book
    Amount: 1
    Order: irrelevant

## ADDITIONAL CONTENT PROCESSING

When adding content using the `Content` entry, the file will additinally be
searched for a comment specifying the its name in the TOC in this format:

    <!-- ePub title: "TOC_NAME" -->

Where `TOC_NAME` is a string not containing the *"* character.

This will, on e-book readers, allow users to jump directly to the content
represented by the document containing this entry.

Optional.

## AUTHOR

Written by nabijaczleweli &lt;<nabijaczleweli@gmail.com>&gt;

## REPORTING BUGS

&lt;<https://github.com/nabijaczleweli/gen-epub-book/issues>&gt;

## SEE ALSO

&lt;<https://github.com/nabijaczleweli/gen-epub-book>&gt;
