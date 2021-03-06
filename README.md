The Allegro web site is generated using Pandoc.

The parts which are common to all pages are stored in the en/_include/* files.

The initial portion of the page (title and sidebar) are generated by running
these files through Pandoc to produce HTML:

    en/_include/before-body
    en/_include/links

    => produces en/_include/before-body.html

The end of the page (footer) is generated from the files:

    en/_include/after-body
    en/_include/links

    => produces en/_include/after-body.html

The files en/_include/in-header, en/_include/before-body.html
en/_include/after-body.html are then included into each page.

The main content of each page is generated for all the files within
a directory, e.g. for the news page:

    en/news/a.header
    en/news/news.2008-11-02
    en/news/news.2008-10-01
    en/news/news.2008-09-10
    en/news/z.footer
    en/_include/links

Notice that the filenames within the directory are sorted, except that
sequences of files with dates in them are *reverse* sorted.

To create a news item, just add a new file in `en/news`.  Old news items
can be moved to `en/oldnews` periodically.

Any content run through Pandoc can be written with Markdown syntax, but you
can also insert any HTML you need.

Files in the static directory are copied directly to the output directory.
