# publishing-reveal-ck-slides

This repository *is* a set of slides.

This repository is referenced in the [reveal-ck wiki][reveal-ck-wiki]
at [Publishing-Slides][reveal-ck-wiki-publishing-slides].

[reveal-ck-wiki]: https://github.com/jedcn/reveal-ck/wiki
[reveal-ck-wiki-publishing-slides]: https://github.com/jedcn/reveal-ck/wiki/Publishing-Slides

## How can a git repository *be* a set of slides?

The `master` branch contains files that configure and serve as general
inputs to a ruby gem called [reveal-ck][rubygems-reveal-ck].

[rubygems-reveal-ck]: http://rubygems.org/gems/reveal-ck

The reveal-ck gem can take these inputs and generate a set of static
HTML files. These files *are* a presentation when viewed in a browser.

Further-- if you take these static file and commit them to the
`gh-pages` branch, then, through the magic of
[Github Pages][github-pages], you'll see the presentation here:
http://jedcn.github.io/publishing-reveal-ck-slides

[github-pages]: https://pages.github.com/

And that's how this repository *is* a set of slides:

* The source of the slides are on `master`, and
* The generated result is on `gh-pages`.
