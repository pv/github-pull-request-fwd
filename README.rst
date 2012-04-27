github-pull-request-rss
=======================

Generate a RSS feed containing Github pull requests and, optionally, the
chatter therein. Or, re-send them via mail.

Usage
-----

    github-pull-request-rss CACHE.json USER/PROJECT > OUT.rss

or (careful!)

    github-pull-request-rss CACHE.json USER/PROJECT -m list@somewhere.org

or

    github-pull-request-rss CACHE.json USER/PROJECT --mbox > OUT.mbox

What mails are generated is determined by the ``last_mailed`` timestamp
in CACHE.json

