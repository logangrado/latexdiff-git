# latexdiff-git

![v0.2.0](https://d25lcipzij17d.cloudfront.net/badge.svg?id=gh&type=6&v=0.2.0&x2=0)

## Overview

`Latexdiff-git` is a tool to help run `latexdiff` on all `.tex` files in a `git` repository across different commits or branches. It is a wrapper around [`latexdiff`](https://git-scm.com) and [`git`](https://git-scm.com).

`latexdiff-git` runs `latexdiff` between all `.tex` files in the current repository and the same files one commit previous. By default, `latexdiff-git` **overwrites** files with their diff'ed version, but this behaviour can be modified with the `--outdir <DIR>` option. I find this very helpful for ensuring that all differences are resolved before committing a new version. 

**`latexdiff-git` works with \include, \input, and \subfiles!** This is because `latexdiff-git` *does not* use the `--flatten` arg to `latexdiff`, but instead runs `latexdiff` on each individual file!

## Installation

Copy `latexdiff-git` somewhere on your system:

```
cp latexdiff-git ~/.bin
```

And ensure that location is in your `PATH`:

```
export PATH=~/.bin:$PATH
```

Add the above line to your `bashrc` to ensure it is always avilable.

## Usage

Simply run `latexdiff-git` in a directory under git source control.

```
latexdiff-git
```

By default, latexdiff-git generates a diff between all `.tex` files in the current directory (including subdirectories), and the second most recent commit `HEAD~1`. To compare to a different commit, or branch, use `latexdiff-git COMMIT`

## Help

For help, use `-h` or `--help`

```
latexdiff-git -h
```

## Changelog
See [CHANGELOG](docs/CHANGELOG.md)

## Alternatives

- [git-latexdiff](https://gitlab.com/git-latexdiff/git-latexdiff) 

  git-latexdiff automaticaly generates a diff'ed PDF between commits, and is very useful for quickly visualizing changes in   `.tex` files between commits. However, if you're interested in combing through those diff's one by one in the `.tex`, it falls short. Not only does git-latexdiff flatten all source files into one big diff, but it also generates the diff in a temp directory. Personally, I prefer the diff files to overwrite my current files, which makes it far easier to find and resolve all the diffs.
