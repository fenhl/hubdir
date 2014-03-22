**hubdir** is a system that helps you keep your github repos organized. It is *not* a git workflow, and works with different (but not all) workflows.

This is hubdir version 1.0.0 ([semver](http://semver.org/)). The versioned API is described below, in the section *The system*.

# The system

This section describes the hubdir system.

## The directories

In the hubdir system, all github repos are organized within the *hub directories*, or *hubdirs*. There are two kinds of hubdir:

1.  the global hubdir at `/opt/hub`, and
2.  the local hubdirs at `~/hub`. Each user can have their own local hubdir.

The global hubdir will be used by default, while the user's local hubdir is used only for staging and when the global hubdir is inaccessible.

## Directory structure

Three different kinds of repos may reside within a hubdir:

1.  Regular repos, located at `hub/<user>/<reponame>`. These track [the default branch](https://help.github.com/articles/setting-the-default-branch) from github and should always stay clean.
2.  Branches, located at `hub/branch/<user>/<reponame>/<branch>`. These work like the regular repos, except they track a different remote branch.
3.  Stages, located at `hub/stage/<user>/<reponame>`. These have more loose restrictions and are where any work happens.

(Thanks to whoever registered [@branch](https://github.com/branch) and [@stage](https://github.com/stage) so these could be used as reserved words.)

## Repo setup

Within a repo, the following rules should be, well, followed:

*   All repos have the following two remotes:
    1.  `origin`, the default remote with the URL set to `git@github.com:<user>/<reponame>.git`
    2.  `readonly`, with the URL set to `https://github.com/<user>/<reponame>.git`
*   Regular repos and branches have no other remotes. For stages, do whatever works best for your git workflow.
*   In multi-user environments, the global hubdir and everything under it should be owned by a group named `hub` and be group read-writeable.
