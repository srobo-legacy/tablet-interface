# SR Tablet Interface

The interface for the tablets contained in the SR 2015 kit.

## Set up

    $ bower install

    $ virtualenv -p /usr/bin/python2.7 venv
    $ source venv/bin/activate
    $ pip install -r requirements.txt

## Running

    $ source venv/bin/activate
    $ ./server.py

You can then go to `http://localhost:8000` in a browser.

## User-code

Run this to test custom components.

    $ source venv/bin/activate
    $ cd usercode
    $ ./server.py

## Firefox

Under Firefox, the application is very slow at the moment. This will be looked into and (hopefully) fixed. Do **not** be tempted to enable the `dom.webcomponents.enabled` property in `about:config` since it causes Firefox to segmentation fault. :unamused:

## Chrome/Chromium

Chrome runs much faster than Firefox on the tablets at the moment. The cause of which seems to be buried somewhere in Polymer since it is changing the prototype of objects using `__proto__` which is known to be slow in Firefox.

If you would like to build Chromium to run on the tablet, [follow the instructions on the Chromium wiki][0].

[0]: https://code.google.com/p/chromium/wiki/AndroidBuildInstructions
