# cloc-author-date
A bash script that counts the lines of code changes for multiple git repos with multiple authors.

```text
Cloc Totals 📊
----------------------------------------

Tim Apple: +498 -1290
Skittles: +245 -9042
Oprah: +4893 -5202

```
## Usage

- Clone the repo
- `$ cd cloc-author-date`
- `$ ./cloc-author-date '<<SINCE>>' '<<AUTHORS>>' '<<OPTIONAL_UNTIL>>'`
  - `'<<SINCE>>'` is a [unix timestamp](https://github.com/git/git/blob/master/Documentation/date-formats.txt). Examples:
    - '1.year'
    - '1.month'
    - '1.day'
    - 'jan 01 1970'
  - `'<<AUTHORS>>'` is a space separated list of git authors
    - git authors can be found by running `git shortlog -sne` in a git initialized repo.
  - `'<<OPTIONAL_UNTIL>>'` is an optional param that takes in a unix timestamp. If nothing is provided, it defaults to the current date and time. Refer to the examples from `'<<SINCE>>'` for a unix time stamp.
- Generate a `repos.txt` file at the root of the cloc-author-date directory (This file is git ignored)
  - Fill the file with SSH or HTTPS clone links separated by new lines. Example:

```
git@github.com:username/repository1
git@github.com:username/repository2
git@github.com:username/repository3
...
```

## Script Examples
```bash
$ ./cloc-author-date '1.year' 'timapple@apple.com skittles@pe.com oprah@aol.com'
$ ./cloc-author-date 'jan 01 2022' 'timapple@apple.com oprah@aol.com'
```
## Notes
- This script will only count lines of code on the main or master branch
