# latexdiff-git

## Overview

Latexdiff-git is a tool to help visualize changes in LaTeX files under git version control. It is a wrapper around [latexdiff](https://git-scm.com) and [git](https://git-scm.com).

By default, `latexdiff-git` runs `latexdiff` on all `.tex` files in the current repository, compared against files one commit previous, `HEAD~1`. By default, `latexdiff-git` **overwrites** files in the current directory with the diff'ed version. I find this very helpful for ensuring that all differences are resolved before committing a new version. This behavior can be modified with the `--no-overwrite` option.

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

## Alternatives

#### [git-latexdiff](https://gitlab.com/git-latexdiff/git-latexdiff) 
git-latexdiff is a full-featured and solid alternative, but didn't fulfill my requirements. Unlike `latexdiff-git`, git-latexdiff generates the diff files in a temporary directory, and deletes them after generating a PDF. However, I prefer the diff files to overwrite my current files, which makes it far easier to find and resolve all the diffs. git-latexdiff also automatically generates and opens a diff'ed PDF.
