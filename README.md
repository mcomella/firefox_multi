firefox\_multi README
====================
firefox\_multi is a Firefox profile multiplexer written in Python. Given a
series of profiles, this script will take the next inactive profile and launch
Firefox with it. If all profiles are active, the script will attempt to recover
any profiles which claim to be active but may have actually crashed. This is
done by verifying that the process of an active profile is no longer running
and deleting the appropriate lock file.

The script supports multiplexing on a shared file system, though recovery
assumes SSH access to remote hosts.

Any profile containing the substring "sync" in its name will be multiplexed.

Some example use cases include running Firefox on multiple xscreens, across
multiple machines on a networked file system, or some combination thereof.

For the best experience, it is recommended that each multiplexed profile is
synced to the same account with [Firefox Sync](https://support.mozilla.org/en-
US/kb/firefox-sync-take-your-bookmarks-and-tabs-with-you).

Usage
-----
  * Create n + 1 profiles containing "sync" in the title where n is the number
of profiles expected to run concurrently
  * Run `firefox_multi`. Any arguments passed to the script should be passed to
the executed Firefox instance
