# create-conventional-changelog

A script for automatically generating a changelog from git history which uses conventional commit messages.
##



### Contents
- [Downloads](#Downloads)
- [Installation](#Installation)
- [Usage](#Usage)
##



### Downloads

Latest version is `v0.1.0`.

- [GitHub releases](https://github.com/termux/create-conventional-changelog/releases).
##



### Installation

1. Run `apt install curl` to install `curl` first and download `create-conventional-changelog`. 

- Latest release:  

  `curl -L 'https://github.com/termux/create-conventional-changelog/releases/latest/download/create-conventional-changelog' -o create-conventional-changelog`  

- Specific release:  

  `curl -L 'https://github.com/termux/create-conventional-changelog/releases/download/v0.1.0/create-conventional-changelog' -o create-conventional-changelog`  

- Master Branch *may be unstable*:  

  `curl -L 'https://github.com/termux/create-conventional-changelog/raw/master/create-conventional-changelog' -o create-conventional-changelog`  

2. Give executable permissions.

   `chmod +x create-conventional-changelog`
##



### Usage

- **`create-conventional-changelog`**

As per conventional commits 1.0.0 specs, the commit message should be structured as follows:

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

Check [` conventional-commits_v1.0.0.md`](conventional-commits_v1.0.0.md) or https://www.conventionalcommits.org/en/v1.0.0 for details on the spec.

The script will add commit messages (subject+body) and their hashes under a markdown heading for the type defined in the commit messages. Further post processing will have to be manually done. All commits that don't match the format with be added under the `<Others>` type. The script considers the types as case-insensitive and are converted to title case for headings.

Make sure to replace `LAST_RELEASE_TAG` at end of changelog file in the compare url.

##### Help:

```
create-conventional-changelog is a script for automatically generating a
changelog from git history which uses conventional commit messages.
https://www.conventionalcommits.org/en/v1.0.0


Usage:
    create-conventional-changelog [command_options] git_dir_path changelog_file_path start_commit_hash end_commit_hash repo_url release_tag

Available command_options:
  [ -h | --help ]    display this help screen
  [ --version ]      display version
  [ -v | -vv ]       set verbose level to 1 or 2


start_commit_hash should be latest commit hash of previous release.

end_commit_hash should be latest commit hash of current release.

repo_url must be in the format: "https://host/<user>/<repo>.
Example: "https://github.com/termux/termux-app"

release_tag must be a valid git tag.
Check http://git-scm.com/docs/git-check-ref-format for details.

Examples:
create-conventional-changelog termux-app changelog.md 9272a757 6c24e6ac https://github.com/termux/termux-app v0.118.0
```
##
