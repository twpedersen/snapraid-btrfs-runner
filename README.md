# Snapraid BTRFS Runner Script

This script is a fork of the [snapraid-runner](https://github.com/Chronial/snapraid-runner) project by Chronial and runs snapraid via [snapraid-btrfs](https://github.com/automorphism88/snapraid-btrfs) by automorphism88 (use [this fork](https://github.com/Suika/snapraid-btrfs) by Suika if using snapper > 0.7). It sends its output to the console, a log file and
via email. All this is configurable.

It can be run manually, but its main purpose is to be run via cronjob/windows
scheduler.

## How to use
* If you don’t already have it, download and install
  [the latest python 2.7](http://www.python.org/getit/). TODO: test script with Python 3.
* Clone this repository via git.
* Copy/rename the `snapraid-btrfs-runner.conf.example` to `snapraid-btrfs-runner.conf` and
  edit its contents. You need to at least configure `snapraid-btrfs.executable`, `snapper.executable`, `snapraid.exectable`, and
  `snapraid.config`.
* Run the script via `python snapraid-runner.py`.

## Features
* Runs `diff` before `sync` to see how many files were deleted and aborts if
  that number exceeds a set threshold.
* Can create a size-limited rotated logfile.
* Can send notification emails after each run or only for failures.
* Can run `scrub` after `sync`

## Changelog for snapraid-btrfs-runner
### (20 Feb 2019)
* Initial release

## Changelog for original snapraid-runner
### Unreleased
* Add support for running `snapraid touch` (by ShoGinn, PR-11)
* Add SMTP TLS support

### v0.3 (20 Jul 2017)
* Limit size of sent emails

### v0.2 (27 Apr 2015)
* Fix compatibility with Snapraid 8.0
* Allow disabling of scrub from command line

### v0.1 (16 Feb 2014)
* Initial release
