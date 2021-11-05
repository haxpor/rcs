[![donate button](https://img.shields.io/badge/$-donate-ff69b4.svg?maxAge=2592000&amp;style=flat)](https://github.com/haxpor/donate)
# rcs

Recursive Code Search for convenient on top of `grap -nr` as shell function.

# Installation

## Manual

Put `.bashrc_rcs` file into your home directory, then edit your `~/.bashrc` or better yet `~/.bash_aliases`
to source such file like following

```
. ~/.bashrc_rcs
```

## Debian/Ubuntu

## Non-pinning way (direct install)

Easiest way to install without having to pinning priority of package (thus a need
to edit some files)

* `sudo add-apt-repository ppa:haxpor/combined`
* `sudo apt-cache showpkg rcs` - due to there is existing same name package offered by Ubuntu
* Grab the version string in `Versions:` section that corresponding to `rcs` package offered by `haxpor`
* `sudo apt install rcs=<version-string>`

## Pinning package with higher priority

See this [article](https://www.claudiokuenzler.com/blog/440/higher-preference-priority-apt-repository-over-another).

# Available flags

* `-f <file-type>` - specify the type of file for the tool to find recursively. The available types can be found via `rcs --help`, 
* `-s <search-term>` - specify the search term, this will be parsed the same if specified to `grep`
* `-i` - specify that searching would be in case-insensitive case
* `-n` - specify that there would be no color output as output from the tool so you can be sure it will be compatible with tool that read its output as input
* `-B` - specify number of lines to include before the matched search term
- `-A` - specify number of lines to include after the matched search term
- `-v` - specify to use inverse search mode, that means not include that specified search term
- `-P` - specify to enable perl regex
- `-o` - specify to output only matched result

# Usage

For some of flags usage, see below.

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
