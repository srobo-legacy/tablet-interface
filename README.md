# Tablet Interface

This repository contains the main code for the tablet interface.

## Errata

### Firefox

Under Firefox, the application is very slow at the moment. This will be looked into and (hopefully) fixed. Do **not** be tempted to enable the `dom.webcomponents.enabled` property in `about:config` since it causes Firefox to segmentation fault. :unamused:

### Chrom(e|ium)

Chrome runs much faster than Firefox on the tablets at the moment. The cause of which seems to be buried somewhere in Polymer since it is changing the prototype of objects using `__proto__` which is known to be slow in Firefox.

If you would like to build Chromium to run on the tablet, [follow the instructions on the Chromium wiki][0].

[0]: https://code.google.com/p/chromium/wiki/AndroidBuildInstructions
