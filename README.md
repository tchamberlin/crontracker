# `crontracker`

Super simple version control for crontabs. Every time your crontab changes, you will be alerted with an email containing the diff. Changes are stored in a git repository at a location of your choosing.

## Install

Clone this repository somewhere. You might optionally symlink `crontracker` to somewhere in the cron daemon's `PATH`

## Configure

Then you'll need to create a cron job for it. For example:

```
*  *  *  *  * crontracker ~/crontracker_log
```

If `~/crontracker_log` doesn't exist, it will be created and `~/crontracker.$USER.$HOSTNAME.txt` will also be created, based on the output of `crontab -l`. On subsequent executions, a new commit will be made if changes to the crontab for that user and host are found.

You'll probably want to reduce the frequency later, but it's nice to have quick iterations at first to make sure things are working.

And that's it! Do this for every user and host that you have crontabs for.
