Content Versioning
==================

Summary
-------

Given a digital asset (source code, binaries, groups of files, images, videos, etc.), run a cryptographically-secure hash over the bits that comprise that asset, and use the hash as the version for that asset.
1. Identify exactly what comprises "an asset". It may be convenient, though not necessary, to tar/zip a group of files together.
2. Pick a currently-known cryptographically-secure Hash function. For example SHA256, as of the time this was last versioned @{{ site.github.build_revision }}
3. Use this hash as the version of that asset. The version of this document is: {{ site.github.build_revision }}
4. Optionally, to avoid ambiguity, prefix the hash function name, separated by a colon, behind the hash value. The unambiguous version of this document is: sha1:{{ site.github.build_revision }}

Example
-------

Want to know precisely how to get the source contents of THIS page you're seeing? The [Github Repository](https://github.com/polyverse-security/contentversioning) is faily obvious. Even if you had a label-based version such as v1.5.2 or release-5, you still wouldn't know whether it's a branch or a tag and whether that ref hasn't been moved.

Thanks to Content Versioning, all need to do is run:
```
git checkout {{ site.github.build_revision }}
```

Or go to the commit URL: [https://github.com/polyverse-security/contentversioning/commit/{{ site.github.build_revision }}](https://github.com/polyverse-security/contentversioning/commit/{{ site.github.build_revision }})

And you'll get the PRECISE state of code from which this page is being displayed. Every time. Accurately. Even a single-bit change to that state of that code, would have caused the hash to break, so you can put your mind at ease.

Introduction
------------

*Content-based Versioning* is a methodology of Versioning that identifies *a specific manifestation of bits*. Whether it be a document, an executable, a package, a system, a hardware schematic or so much more. A *version* of that asset is the unambiguous identification of that exact asset.

Traditional Label-based Versioning, one wherein you apply some arbitrary label as a version, does not scale well in an agile and experimentative world. It leads to confusion and conflict. The ability to name things accurately, reliably, consistently and in a manner that anyone else can verify that they are looking at exactly what you meant them to look at (non-repudiability) is an essential tool in the agile security sandbox.

Content Versioning has many distinct advantages over label-based versioning. First and foremost, you no longer have to maintain a correlation table that ties a particular label to a particular asset. Secondly, you can verify if the asset you have is the one that you wanted, without making external service calls or referencing metadata. Third, chain-of-trust becomes a lot easier - instead of communicating an asset label, some sort of signing key, and some sort of additional verification has, all you ever do is communicate the single hash that conveys exactly what the receipient should get.

It also brings a lot of auxiliary benefits such as never having to worry about what the prefixes/suffixes should be, what they mean, etc.

Why Linear Versioning is insufficient
---------------------------------------

In the modern world of agile development, progress is not linear in nature. Things don't progress in an incremental fashion, and an incremental release does not indicate progress. Innovation happens through forks, branches, rewrites, and experiments. It truly is, and therefore mimics biological evolution. New adaptations happen, sometimes adaptations fork off and become new things entirely. Sometimes different branches merge. Some lineages simply die out and go extinct.

We therefore believe that versioning these innovations on a linear scale leads to a great deal of confusion, conflict and awkward workarounds when releasing from different branches, or when releasing from different repositories. Furthermore, when taking dependencies, a "version" is a fairly broad stroke to determine based on. For example, when a breaking change happens across versions, it rarely is breaking for all consumers. Alternately, a non-interface change that doesn't break interfaces, but breaks behavior, can easily be a breaking change for some consumers.

In practice, versioning merely becomes a discriminant, to discriminate between two manifestations of a component. It is pragmatically no different than assigning a monotonically increasing timestamp.

A better way to resolve Dependency Hell
----------------------------------------

All versioning systems are inevitably, in one way or another, intended to resolve Dependency Hell. Label-based versioning though, still ends up with challenges because references can change underneath you. Like we mentioned above, it is a fallacy to think that all interface changes are breaking, and it is an equal fallacy to think that non-interface changes are not breaking.

The only way to accurately express a dependency, is based on the contents of that dependency. What does it contain? Does it contain the libraries you want? Does it contain the code you want? Does it have the interfaces you want? Does it have the features you want?

Content Versioning is a better and more strict way of expressing dependencies, and when combined with feature-detection, a better forcing function to make safer upgrades. Insteading of expressing some awkward generic rule based on arbitrary-assigned labels, you are forced to express rules based on constraints you have on the contents of that dependency.

In our opinion, and through experience, Content Versioning has prevented us from picking up broken packages or security vulnerabilities, and also helped us ensure concretely that we have specific patches or fixes that we expect - based on what was actually contained in those binaries.


FAQ
---

### How do I determine which version comes first? How can I ensure I have the latest and greatest version?

A fundamental requirement of Content Versioning is that you not think of content as linear in terms of "first" or "second". In fact it is one of the greatest advantages of using ConVer. You have better assertions about actual content of an entity.

This means that you now have a good forcing function to ensure that "latest and greatest" isn't merely a matter of someone incrementing a string, but rather ensuring that the contents are what you expect.


About
-----

The Content Versioning specification is authored and sponsored by [Polyverse Corporation](https://polyverse.io).

If you'd like to leave feedback, please [open an issue on
GitHub](https://github.com/polyverse-security/contentversioning/issues).


License
-------

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

Creative Commons - Attribution 4.0 International (CC BY 4.0)
https://creativecommons.org/licenses/by/4.0/
