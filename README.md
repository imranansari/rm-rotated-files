# Remove rotated files

This script deletes log files that are created by various kinds of log file rotations.

Contents:

* [Introduction](#introduction)
* [Which files?](#which-files)
* [Related](#related)
* [Compatibility notes](#compatibility-notes)
* [Tracking](#tracking)


## Introduction

Syntax:

    $ rm-rotated-files <dir>

Example:

    $ rm-rotated-files /var/log


## Which files?

Compressed files: 

  * Files with extensions that are known to be compressed or archived.

  * Examples: .bz2, .bzip, .gz, .tar, .tgz, .zip, .7zip

Old files:

  * Files with extensions that are typically for old files.

  * Examples: .old, .bak, .tmp

Numbered files:

  * Files with names that end in a separator then number:

  * Examples: foo.1, foo-2, foo_3, etc.

Datestamped files:

  * Files with names that end in a separator then ISO date.

  * Examples: foo-2017-12-31, foo_2017_12_31, etc.


## Related

These scripts are for related purposes:

  * [rm-compressed-files](https://github.com/SixArm/rm-compressed-files)

  * [rm-dated-files](https://github.com/SixArm/rm-dated-files)

  * [rm-numbered-files](https://github.com/SixArm/rm-numbered-files)

  * [rm-rotated-files](https://github.com/SixArm/rm-rotated-files)


## Compatibility notes

We prefer to be more compatible rather than system-specific.

  * To delete files, we prefer `-exec rm` vs. `-delete`.
    The former is more compatible, the latter is faster.

  * To regex match, we prefer patterns to be basic vs. extended.
    The former is more compatible, the latter is more modern.

  * We prefer POSIX code vs. shell-specific code.

  * We prefer the code to be more DAMP than DRY.
    For example, the code has separate name matching 
    for `.bz` and `.bz2`, even though we could combine these.


## Tracking

  * Command: rm-rotated-files
  * Website: http://sixarm.com/rm-rotated-files
  * Cloning: https://github.com/sixarm/rm-rotated-files
  * Version: 4.0.0
  * Created: 2013-12-09
  * Updated: 2019-01-21
  * License: GPL
  * Contact: Joel Parker Henderson (joel@joelparkerhenderson.com)
  * Tracker: 0f5f883770a0a2e85c7ec9a0c8296402
