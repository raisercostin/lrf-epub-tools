# lrf-epub-tools

[![Download](https://api.bintray.com/packages/raisercostin/maven/lrf-epub-tools/images/download.svg)](https://bintray.com/raisercostin/maven/lrf-epub-tools/_latestVersion)

## Desciption
From [https://www.mobileread.com/forums/showthread.php?t=28707](https://www.mobileread.com/forums/showthread.php?t=28707):

Another tool, credits to scotty1024 (LRFParse.java), Bruno Lowagie (iText) and people at apache jakarta project, xHTMLRenderer project and others right now I cannot remember.

It can convert LRF files to RTF, PDF, HTML and EPUB. Also can merge LRF and PDF books in one big PDF with TOC, and merge EPUB files into one. And now you can view epub files (use page and key down/up).

You can convert PDFs to EPUB using this tool.
And starting at version 0.9.193, you can conver MS Word 2007 (docx) files to EPUB
v0.9.204 can deal with all scrambled and/or compressed streams

New version 0.9.236 use latest versions of pdfbox, iText and some other libs. For devs: LRFTools is now a Maven project.

Usage:
http://code.google.com/p/lrf-epub-tools/

Download:
http://code.google.com/p/lrf-epub-tools/downloads/list

ChangeLog:
http://code.google.com/p/lrf-epub-tools/updates/list

## How to use
Actions:

convertLRF dir (-d dirOut |-z zipfile) (-XML|-PDF|-RTF|-HTML|-EPUB) (options)
Converts to XML, PDF, RTF and/or HTML every LRF file in 'dir' recursively. You can specify more than one format conversion simultaneously. Converted files go to the same place as original, except if you specify '-z zipfile', then go to zipfile; or '-d dir', then output files are created in dirOut replicating the same original directory tree structure.
(options) one or more of:

-A4 : Means normal paper size (trying to reflow)
-rf nn : Fonts Sizes, nn is a percentage of resistance to change size of font
-catpar str: Try to merge paragraphs not ending with '.', ':','?' this way:

para1+str+para2
-repl "str1" "str2" : Replace instances of str1 (in a block) for str2
-noo : No overwrite existing files.
-noe : No Embed OTF fonts on epub files.
-nopb: Do not emit page breaks.
You cannot output HTML files to a zipfile right now.
convertPDF dir (-d dirOut) [-noo|-SVG|-noe|-nopb]
Converts every PDF in 'dir' (with recursion) to EPUB format. -SVG means use batik to generate Scalable Vector Graphics for each page Other options same as convertLRF.
convertDOCX dir (-d dirOut) [-noo|-noe|nopb]
Converts every OpenXML file (Word 2007 docx files) to EPUB format. Other options same as convertLRF.
view
Shows GUI to view epub files.
updfmd dir
Search dir recursively, expecting PDF filenames 'BookAuthor-BookTitle.pdf' and modifies metadata of PDF to reflect BookAuthor and BookTitle so our Sony PRS can catalog the book conveniently.
mergePDF dir -o grouped.pdf
Merge all PDF and LRF files contained at dir (with recursion) into one new PDF file with a TOC pointing to each old single document. LRF files are converted first to PDF.
mergeEPUB dir -a author -t title -o grouped.epub
Merge all EPUB files contained at dir (with recursion) into one new EPUB file with a TOC pointing to each old single document.
