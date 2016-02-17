There are two sets of content for testing. One is the original content from a profvis htmlwidget, and the other is simplified content that may be useful for testing.


## Original content

The `original` directory contains files for a working profvis visualization. Processing it with pandoc using the same command line as RStudio takes forever (>15 minutes):

```sh
cd original/viewhtml34b530c7198f

time /usr/lib/rstudio/bin/pandoc/pandoc +RTS -K512m -RTS index.html --from markdown_strict --output ../viewer-rpubs-34b57e801fca.html --self-contained --template ../file34b55d5a73f4.html
```

With `--from markdown` instead of `--from markdown_strict`, it takes about 3.5 seconds on my computer.



### Simplified content


In the `simplified-100kb` directory is a stripped-down version of the HTML with ~100KB of text in a `<script>` tag. This may be useful for testing.

It takes about 3 seconds to convert using pandoc with the following command:

```sh
cd simplified-100kb

time /usr/lib/rstudio/bin/pandoc/pandoc +RTS -K512m -RTS index.html --from markdown_strict --output output.html --self-contained --template template.html
```

Using `--from markdown` or `--from commonmark` results in much faster processing.


The `simplified-50kb`, `simplified-150kb`, and `simplified-200kb` directories are essentially the same, but with varying amounts of data.
