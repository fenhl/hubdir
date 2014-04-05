This document is an example workflow that works with hubdir, but is not part of the spec. You can link to it from your project, or include a copy and modify it if you want. It also applies to the hubdir project itself.

# Contributing

This document includes general guidelines that applies to all contributions, as well as specific guidelines for project members acting directly on the repo, and third parties sending pull requests.

## General

*   This project's workflow is based on the workflow described at http://nvie.com/posts/a-successful-git-branching-model/ and unless explicitly stated otherwise, everything said in that guide also applies here.
*   `--no-ff` adds useless clutter. Don't use it.
*   The `develop` branch is called `dev` instead.
*   Non-API-relevant documentation may be changed on `master` and without a new release, and is then merged back into `dev`.

## Pull requests

*   Fork from `dev` and send the pull request back into `dev`.
    *   That is, unless you're only changing non-API-relevant documentation, e.g. fixing a typo in the readme. In this case, you may alternatively fork from `master` and merge back into `master`.
*   `dev` may be merged into existing forks or open pull requests at any point to avoid larger merge conflicts and to encourage tighter integration of the feature with other new features introduced to `dev`.
*   Don't touch the version number.

## For project members

*   Everything is always pushed to and pulled from the github repo. Don't cross-reference other project members' remotes.
*   `dev` may be merged into existing feature branches at any point to avoid larger merge conflicts and to encourage tighter integration of the feature with other new features introduced to `dev`.
*   Release and hotfix branches omit zeroes at the end of the version number. For example, call the branch for version 1.2.0 `release-1.2` instead of `release-1.2.0`.
*   Tag releases on `master` using github's Releases feature.
