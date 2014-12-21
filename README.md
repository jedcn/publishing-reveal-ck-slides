# publishing-reveal-ck-slides

This repository *is* a set of slides.

This repository is referenced and used as an example in the
[reveal-ck wiki][reveal-ck-wiki] at
[Publishing-Slides][reveal-ck-wiki-publishing-slides].

[reveal-ck-wiki]: https://github.com/jedcn/reveal-ck/wiki
[reveal-ck-wiki-publishing-slides]: https://github.com/jedcn/reveal-ck/wiki/Publishing-Slides

## How can a git repository *be* a set of slides?

The `master` branch contains files that configure and serve as general
input to a ruby gem called [reveal-ck][rubygems-reveal-ck].

[rubygems-reveal-ck]: http://rubygems.org/gems/reveal-ck

The reveal-ck gem takes this input and generates a set of static HTML
files. These files *are* a presentation when viewed in a browser.

Further-- if you take these static file and commit them to the
`gh-pages` branch, then, through the magic of
[Github Pages][github-pages], you'll see the presentation here:
http://jedcn.github.io/publishing-reveal-ck-slides

[github-pages]: https://pages.github.com/

And that's how this repository *is* a set of slides:

* The source of the slides are on `master`, and
* The generated result is on `gh-pages`.

See [slides.md](slides.md) for the slide source and
http://jedcn.github.io/publishing-reveal-ck-slides for the generated
result.

---

# Details

If you're looking to do the same thing, here's what I did:

### Create Slides as you normally would

First-- I created all of my slides initially and commited them on the
`master` branch.

### Create a gh-pages branch

Next, I created and pushed up some placeholder content to Github Pages
with the following commands (from
[these official instructions][github-github-pages]):

[github-github-pages]: https://help.github.com/articles/creating-project-pages-manually/

```sh
cd /tmp
git clone https://github.com/jedcn/publishing-reveal-ck-slides
cd publishing-reveal-ck-slides
git checkout --orphan gh-pages
git rm -rf .
echo 'Coming Soon' > index.html
git add index.html
git commit -m "Barebones gh-pages commit"
git push origin gh-pages:gh-pages
rm -rf /tmp/publishing-reveal-ck-slides
```

These commands create a temporary clone in the `/tmp/` directory. I
had my original clone elsewhere on my computer.

### Clone gh-pages into ./slides/

Then I went back to my original clone, made sure `slides` was in my
.gitignore, and ran the following commands:

```sh
rm -rf slides
git clone https://github.com/jedcn/publishing-reveal-ck-slides.git --branch gh-pages --single-branch ./slides
```

### Finally, re-generate and push

```
bundle exec reveal-ck generate
cd slides
git add .
git commit -m "Files after initial reveal-ck generate"
git push origin gh-pages:gh-pages
```

And now the slides are available at:
http://jedcn.github.io/publishing-reveal-ck-slides
