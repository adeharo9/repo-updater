# Repository updater
Script for automatic repository update over bash terminal (although it shouldn't be difficult to port to other terminals).

## Supported VCS
Currently supported version control systems are:

- Git
- Mercurial
- Subversion

## Installation
I like to put all my utility scripts under `~/.scripts` and add this directory to my path by using the following command:

```
export PATH="$PATH:$HOME/.scripts"
```

I also tend to make this change persistent by appending that line to the end of my `.bashrc` file so it is loaded at the beginning of each session.

Obviously, these are only personal preferences; you can choose your own way to do it :)

## How to use it?
The script takes a list of one or more directories as input: it enters each of those directories in search for repositories on its immediate subdirectories:

- If a subdirectory is a repository, it tries to update it.
- If it is not, it silently ignores it.

In order to detect what kind of VCS a repository uses, it searches for the specific hidden folders of each of them in the following order:

1. `.git`
2. `.hg`
3. `.svn`

Which means in case you have mixed VCS (typical case is a SVN repository inside a git one), they'll be detected following the former order (in the example, it'll be detected and updated as a git repository, not as a subversion one).
