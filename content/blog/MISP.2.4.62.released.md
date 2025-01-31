---
title: MISP 2.4.62 and PyMISP 2.4.62 released
date: 2017-01-26
layout: post
banner: /img/blog/misp-small.png
---

A new version of MISP [2.4.62](https://github.com/MISP/MISP/tree/v2.4.62) has been released, including bug fixes and new features.

MISP feed has been expanded to support local feed allowing users to import feeds from local directories (if MISP format) or
local files (like free-text or CSV import) in addition to the network feeds.

The API restsearch has been extended to allow two new search parameters:

  - ```to_ids```, with the following options
    - false (default): include all attributes, no matter the to_ids flag
    - true: include only to_ids attributes
    - "exclude": exclude attributes marked to_ids

  - ```deleted``` with the following options
    - false (default): only include non deleted attributes
    - true: include deleted attributes
    - "only": ONLY include deleted attributes

At the same time, [PyMISP](https://github.com/MISP/PyMISP) has been released as version 2.4.62. PyMISP has been updated to support the recently added functions in the [automation API of MISP](https://www.circl.lu/doc/misp/automation/index.html).

PyMISP documentation is available as [HTML](http://pymisp.readthedocs.io/en/latest/) or [PDF](https://media.readthedocs.org/pdf/pymisp/master/pymisp.pdf).

If you would like to write software using the MISP API with PyMISP, there is an [extensive list of examples](https://github.com/MISP/PyMISP/tree/master/examples) in the PyMISP repository.

A big thanks to all the users who gave feedback and contributors who helped us improve MISP.

The full change log is available [here](https://www.misp.software/Changelog.txt).

Don't hesitate to [open an issue](https://github.com/MISP/MISP/issues) if you have any feedback, found a bug or want to propose new features.
