This Week in Python
===================

(Under Construction)

Content for [thisweekinpython.org](https://thisweekinpython.org). Made available under CC-BY-SA.



## PRs for next issue are now being accepted

Check the `drafts` directory for more details.

## How I get PR lists:

```
git log --author=bors --since='MM/DD/YYYY 12:00PM' --until='MM/DD/YYYY 12:00PM' --pretty=oneline > ~/entropy/twir.txt
# edit in vim to get rid of everything but PR number, copy into clipboard
for pr in $(xsel -ob); do firefox https://github.com/python/cpython/pull/$pr; sleep 0.07; done
# wait a long time...
# write TWIR
```

Alternately use GitHub search:

```
https://github.com/python/cpython?q=is%3Apr+is%3Amerged+updated%3A2020-07-03..2014-11-10
```

## How I get new contributors:

Use the included `new_contribs.sh` script:

  new_contribs.sh <date>

## Building

Ensure you have SASS installed. The easiest way to get it is via `gem`, the
Ruby package manager.

```
env SASS_BIN=$HOME/.gem/ruby/*/bin/sass pelican content -s pelicanconf.py
```

### To build the newsletter

* Generate the HTML
  ```
  TWIR_NEWSLETTER_THEME=1 pelican --delete-output-directory content
  ```
* Copy the HTML and inline CSS at http://zurb.com/ink/inliner.php - (MailChimp's inliner doesn't remove the CSS from `<head>`).
* Send the newsletter (we currently use MailChimp).

## Attribution

Inspired and bootstrapped using the wonderful emberian/this-week-in-rust project. Contents from that site are CC-BY-SA.

All code Copyright 2014 Ember Arlynx, made available under [the MIT
license](http://mit-license.org/).
