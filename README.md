# Repository updater
Script for automatic repository update over bash terminal (although it shouldn't be difficult to port to other terminals).

## Supported VCS
Currently supported version control systems are:

- Git
- Mercurial
- Subversion

## How to
The script takes a list of one or more directories as input: it enters each of those directories in search for repositories on its immediate subdirectories:

- If a subdirectory is a repository, it tries to update it.
- If it is not, it silently ignores it.

In order to detect what kind of VCS a repository uses, it searches for the specific hidden folders of each of them in the following order:

- .git
- .hg
- .svn

Which means in case you have a mixed VCS (typical case is a SVN repository inside a git one), they'll be detected following the former ordering.
