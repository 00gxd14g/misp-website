---
title: MISP 2.4.154 released including tools for managing rapidly changing communities
date: 2022-03-02
layout: post
banner: /img/sharing-group-blueprints.png
---

MISP 2.4.154 released with a host of new features and fixes, including some new tools that help us navigate the current geo-political landscape when sharing information.

# Sharing group blueprints

Difficult times often call for radical measures, with the recent world events we've seen more and more communities rapidly reorganising as well as new large communities being established. Sharing information with only subsets of communities has become ever more important and whilst we've had the tools to facilitate this in MISP for a long time, rapidly managing different, often overlapping groups has been difficult.

Sharing group blueprints allow us to programmatically define reusable blueprints for generating sharing groups, based on inheritance and various filters to automate the task of maintaining the groups.

Sharing group blueprints accept JSON objects based on which they generate a sharing group each, where various filters can be set for the decision making. The syntax allows for boolean operators as well as the use of organisation metadata and existing sharing group inheritance. This can also be used to create derivative groups with certain members being excluded, for example the below would be such an example:

```
{
   "AND": {
       "OR": {
           "org_sector": "Financial",
           "sharing_group_id": 127
       },
       "NOT": {
           "org_nationality": [
               "Russia",
               "Russian Federation",
               "Belarus",
               "Republic of Belarus"
           ]
       }
   }
}
```

The above would generate a sharing group out of all organisations present in sharing group 127, any organisation that has "Financial" as its type, but excluding any of the specifically negated countries' organisations.

This system thrives on well maintained organisation lists, so make sure that you put in the extra effort of contextualising your organisations!

Once a blueprint is created, you can review the organisations to be included and if you are satisfied, create the actual sharing group by clicking on (re)generate sharing group.

![sharing-group-blueprint](https://user-images.githubusercontent.com/3668672/158998299-52bfc259-ad7a-43a7-8287-a1f368cc9845.png)

One of the advantages of this system is that the regeneration can be run at any time, for a single sharing group or for all, via the interface or the API. This means that creating a cron job that updates all sharing groups based on the rules regularly is trivial, ensuring that for example inherited organisations via updated child sharing groups are updated continuously.

# Populate events using MISP JSON elements

There's a new way to populate an individual, existing event: by uploading a JSON file containing MISP elements (such as attributes, objects, tags, galaxies, etc), one can now easily paste JSON blobs into a form that an be accessed by clicking on "Populate from..." and selecting "Populate using a JSON file containing MISP event content data".

# Improvements to the OIDC authentication

A host of improvements and fixes, including the switch to a new library, developed by Jakub Onderka.

# Acknowledgement

We would like to thank all the [contributors](https://www.misp-project.org/contributors), reporters and users who have helped us in the past months to improve MISP and information sharing at large. This release includes multiple updates in [misp-objects](https://www.misp-project.org/objects.html), [misp-taxonomies](https://www.misp-project.org/taxonomies.html) and [misp-galaxy](https://www.misp-project.org/galaxy.html).

As always, a detailed and [complete changelog is available](https://www.misp-project.org/Changelog.txt) with all the fixes, changes and improvements in MISP core.
