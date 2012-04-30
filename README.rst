github-pull-request-fwd
=======================

Grab Github pull requests, and generate a RSS feed, a mail mbox, or just send
the mails. Optionally, all chatter therein can be included.

Can be called periodically, e.g., in crontab, or activated by a trigger, for
example a Github commit hook.

Usage
-----

::

    github-pull-request-fwd rss CACHE.json USER/PROJECT > out.rss
    github-pull-request-fwd mbox CACHE.json USER/PROJECT > out.mbox

or (careful!)::

    github-pull-request-fwd mail CACHE.json USER/PROJECT RECEIVER@SOMEWHERE

Generate an RSS feed from Github Pull Requests and all comments in
them.

What mails are generated is determined by the ``last_mailed`` timestamp
in CACHE.json, which you can adjust with the ``--catchup-mails`` option.

Options:
  -h, --help            show this help message and exit
  -p, --pr-only         produce feed containing only the pull requests
  -n, --no-update       don't download updated data from the internet
  -c COUNT, --max-count=COUNT
                        rss: maximum number of feed items (default: 100)
  -t TTL, --ttl=TTL     rss: time-to-live in minutes (default: 360)
  --smtp-server=HOST    mail: send mail via given SMTP server, instead of
                        localhost
  --catchup-mail=DATE   mail: consider only mails after DATE
  --mail-template=FILE  mail: template file for mails
  --print-template      mail: print the default mail template
