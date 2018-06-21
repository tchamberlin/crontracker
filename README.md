# `crontracker`

Super simple version control for crontabs. Every time your crontab changes, you will be alerted with an email containing the diff. Changes are stored in a git repository at a location of your choosing.

## Install

Clone this repository and place `crontracker` somewhere in your path. For example:

    $ git clone https://github.com/tchamberlin/crontracker.git
    $ ln -s PATH_TO_CRONTRACKER ~/bin/crontracker
    
## Configure
    
Then you'll need to create a cron job for it. For example:
    
    *  *  *  *  * crontracker ~/crontracker_log
    
If `~/crontracker_log` doesn't exist, it will be created and `~/crontracker.$USER.$HOSTNAME.txt` will also be created, based on the output of `crontab -l`.

You'll probably want to reduce the frequency later, but it's nice to have quick iterations at first to make sure things are working.

And that's it! Do this for every user and host that you have crontabs for.
