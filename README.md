Chiron
======

Chiron is a zephyrbot that listens for zephyrs containing ticket numbers, looks
up the ticket in an appropriate bugtracker, and responds with the ticket title
and URL. Over time, the definition of "bugtracker" has broadened --- it
includes actual bugtrackers like Debathena's, but also MIT class numbers and
bible verses.

Features
--------

- Supports "tickets" in more than two dozen different "bugtracker" instances --- see `bugtrackers.txt` for a list
- Generic support for projects using
    - Trac
    - Github Issues
    - Bugzilla
- Responds to both classed and personal zephyrs
    - For personal zephyrs, will reply-all to CC'd messages

Running
-------

Chiron requires [Evan Broder's
`python-zephyr`](https://github.com/ebroder/python-zephyr).

Chiron must be run with tickets so that it can sub to incoming zephyrs. You may
find [`k5start`](http://www.eyrie.org/~eagle/software/kstart/) helpful for
keeping current tickets available.

You can run it subbed to personals only with `./main.py`.

Primary production deployment
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Alex Dehnert <adehnert> runs the primary Chiron instance, and is generally
happy to add additional matchers, fetchers, or classes. To request changes,
please [file an issue (or pull request) on
Github](https://github.com/sipb/chiron/issues/), zephyr him, or send mail to
chiron@mit.edu.

Private deployments
~~~~~~~~~~~~~~~~~~~

If you want to run your own private production Chiron instance, you can also do
that. By default, `main.py` will only sub to personals; when run with the
`--classes` option it will sub to a variety of additional classes. Feel free to
crib from `main.py` in setting up your own Chiron instance, or run it subbed
only to personals. However, please ensure that if you run a Chiron instance
that subs to non-personals, it listens on different classes and/or uses
different matchers than the primary instance, so that users don't receive
multiple replies to their zephyrs.
