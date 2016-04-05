# Create Git Commit Template

Create a file to hold your template, e.g. git-commit-template.txt.
Put in whatever you want to remember, just be sure to keep everything
commented out (via #) or it will be in the actual message.


Run `git config --global commit.template /path/to/git-commit-template.txt`
or edit `~/.gitconfig` and add `template = /path/to/.gitmessage.txt`
under the `[commit]` block.


Example:

```
# <type>: <subject>

# <body>

# <footer>

# Type should be one of the following:
# * :package: **feat** (new feature)
# * :bug: **fix** (bug fix)
# * :book: **docs** (changes to documentation)
# * :art: **style** (formatting, missing semi colons, etc; no code change)
# * :fire: **refactor** (refactoring production code)
# * :no_entry: **remove** (remove code and/or files)
# * :white_check_mark: **test** (adding missing tests, refactoring tests; no production code change)
# * :nut_and_bolt: "**chore** (updating grunt tasks etc; no production code change)
# * :eyeglasses: **linting** (remove linter warnings/errors; no breaking code changes)

# Subject should use impertivite tone, say what you did, and be less than 50 characters
# The body is for optional detail about changes made
# The footer is optional to note pull request/issue number; e.g. fixes #123
```
