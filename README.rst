github-pull-request-rss
=======================

Generate a RSS feed, mail mbox (or just send the mails), containing
Github pull requests and, optionally, the chatter therein.

Can be called periodically, e.g., in crontab, or otherwise activated
by trigger.

Usage
-----

::

    github-pull-request-rss rss CACHE.json USER/PROJECT > out.rss
    github-pull-request-rss mbox CACHE.json USER/PROJECT > out.mbox

or (careful!)::

    github-pull-request-rss mail CACHE.json USER/PROJECT RECEIVER@SOMEWHERE

Generate an RSS feed from Github Pull Requests and all comments in
them.

What mails are generated is determined by the ``last_mailed`` timestamp
in CACHE.json, which you can adjust with the ``--catchup-mails`` option.

Options:
  -h, --help            show this help message and exit
  -p, --pr-only         produce feed containing only the pull requests
  -c COUNT, --max-count=COUNT
                        maximum number of feed items (default: 100)
  -n, --no-update       don't download updated data from the internet
  -t TTL, --ttl=TTL     time-to-live in minutes (default: 360)
  --smtp-server=HOST    send mail via given SMTP server, instead of localhost
  --catchup-mail=DATE   consider only mails after DATE
  --mail-template=FILE  template file for mails
  --print-template      print the default mail template
