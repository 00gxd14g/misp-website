---
title: MISP 2.4.52 released including new features and major improvements
date: 2016-10-07
layout: post
banner: /img/blog/misp-small.png
---

We are glad to announce MISP 2.4.52 including new features, improvements and bug fixes.

The following new features were introduced:

 - Freetext feed import: a flexible scheme to import any feed available on Internet and incorporate them automatically in MISP. The feed imported can create new event or update an existing event. The freetext feed feature permits to preview the import and quickly integrates external sources.

![External feed in MISP - an example of external feed configured](/img/blog/misp/freetext-feed.png "{class='img-responsive'}")

 - [Bro NIDS](https://www.bro.org/) export added in MISP in addition to Snort and Suricata.

 - A default role can be set allowing flexible role policy.

 - Functionality to allow merging of attributes from a different event.

 - Many updates and improvement in the MISP user-interface including filtering of proposals at index level.

Bug fixes and improvements:

 - XML STIX export has been significantly improved to ensure enhanced compatibility with other platforms.
 - Bruteforce protection has been fixed.
 - OpenIOC export via the API is now possible.
 - Various bugs at the API level were fixed.

[MISP taxonomies](https://github.com/MISP/misp-taxonomies) and [warning-lists](https://github.com/MISP/misp-warninglists) have been updated to the latest version.

For more information about the updates, check the [changelog](/Changelog.txt).

We thank all the contributors, bug finders, testers and users of the MISP platform.
