[![donate button](https://img.shields.io/badge/$-donate-ff69b4.svg?maxAge=2592000&amp;style=flat)](https://github.com/haxpor/donate)
# rcs

Recursive Code Search for convenient on top of `grap -nr` as shell function.

# Installation

Put `.bashrc_rcs` file into your home directory, then edit your `~/.bashrc` or better yet `~/.bash_aliases`
to source such file like following

```
. ~/.bashrc_rcs
```

# Usage

After installation, source either your `~/.bashrc` or `~/.bash_aliases` with `source <file>` (substitute
your bash file into it), then you're ready to use it.

You can see full detail of help message included list of supported formats by executing the following

```
rcs --help
```

Ex. Search for target text of `void OnChange(` via `-s` from header files via `-f`

```
rcs -s void\ OnChange\( -f header
```

Ex. Same but ignore case via `-i`

```
rcs -s void\ OnChange\( -f header -i
```

Ex. Same but also output before & after number of lines via `-B <N>` and `-A <N>` respectively

```
rcs -s void\ OnChange\( -f header -i -B 3 -A 3
```

Ex. Same but supress color output via `-n` (so it would work correct with tools that don't understand color code from shell)

```
rcs -s void\ OnChange\( -f header -i -B 3 -A 3 -n
```

# License
Wasin Thonkaew, MIT
