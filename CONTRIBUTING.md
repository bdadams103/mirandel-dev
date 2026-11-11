# Working on Mirandel

The live site deploys automatically from `main` through GitHub Pages.
Nothing goes to `main` without Ben looking at it first.

## The rule

1. **Never commit directly to `main`.** All work happens on a branch,
   named `draft/<short-description>` (for example `draft/ferry-falls-towns`).
2. **Push the branch and open a pull request.** The pull request is the
   review unit, not the code diff.
3. **Ben reviews a rendered preview of the branch before it merges.**
   GitHub Pages does not build previews for pull requests, so the preview
   is a rendered copy of the branch's pages (an artifact or screenshots),
   provided with the pull request. Review how it looks and plays in the
   browser, and say go or ask for changes.
4. **Merge only after approval.** Merging the pull request into `main`
   is what publishes to the live site, because Pages deploys `main`
   automatically.

## Enforcement

- GitHub branch protection on `main` (Settings, Branches): require a pull
  request before merging, block direct pushes. This makes the rule
  mechanical instead of a promise. If it is not turned on yet, turn it on
  before the next change.

## If a preview looks wrong

Fix it on the same branch and push again. A fresh preview is provided
with the updated branch. Do not merge a branch whose preview has not
been reviewed.

## Hosting note

Production is GitHub Pages, deploying from branch `main`, folder `/`.
There is also a copy of the site at mirandel.netlify.app, but it is not
connected to this repository, so it does not update when `main` changes.
Do not treat the Netlify copy as the live site.
