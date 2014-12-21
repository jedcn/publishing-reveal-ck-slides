# Publishing
## Slides
with reveal-ck

***

# Overview

---

## Use Two Branches

* `master`
* `gh-pages`

---

`master` contains reveal-ck inputs

(like `slides.md`)

---

`gh-pages` contains generated slides

(contents of the `slides/` directory)

***
***

# Branch Creation

---

`master` is created by default when you use git.

---

Create `gh-pages` when you're ready to publish slides.

---

Follow these [official instructions provided by github][github-gh-pages].

[github-gh-pages]: https://help.github.com/articles/creating-project-pages-manually/

***
***

# Branch Layout

---

Once you have two branches: `master` and `gh-pages`, where do clones
live on your file system?

---

I suggest that `master` be cloned to wherever you want, and that you
gitignore `slides/`. Then..

---

I suggest that you create a second clone in `slides/` and keep this on
the `gh-pages` branch.

---

If you do this.. you will naturally generate a fresh set of slides
into `slides/`, then cd into that directory, commit, and push up.

***

# Viewing Slides

---

Pushing to `gh-pages` will cause you to use Github Pages.

---

Your slides will be available at: http://$you.github.io/$project.

---

## If...

| Item     | Value                        |
| ---------| ---------------------------- |
| $you     | jedcn                        |
| $project | publishing-reveal-ck-slides  |

---

## Then

http://jedcn.github.io/publishing-reveal-ck-slides
