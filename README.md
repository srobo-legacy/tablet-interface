# SR Tablet Interface

The interface for the tablets contained in the SR 2015 kit.

## Set up

External libraries are managed with `bower`, therefore you must have it installed and also make sure to install all the packages before testing:

    $ bower install

To run the server, you must install some dependencies

    $ pip install twisted Flask
    $ git clone git@github.com:tavendo/AutobahnPython.git
    $ cd AutobahnPython
    $ python build.py install
    $ cd ..

## Running

    $ ./server.py

You can then go to `http://localhost:8000` in a browser.


## User-code

You can also run an example user code which provides a custom component.

    $ cd usercode
    $ ./server.py

**Note:** only works when connected via `localhost`.

