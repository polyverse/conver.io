Summary
-------

Given a digital asset (source code, binaries, groups of files, images, videos, etc.), run a cryptographically-secure hash over the bits that comprise that asset, and use the hash as the version for that asset.
1. Identify exactly what comprises "an asset". It may be convenient, though not necessary, to tar/zip a group of files together.
2. Pick a currently-known cryptographically-secure Hash function. For example SHA256, as of the time this was last versioned @{{ site.github.build_revision }}
3. Use this hash as the version of that asset. The version of this document is: {{ site.github.build_revision }}
4. Optionally, to avoid ambiguity, prefix the hash function name, separated by a colon, behind the hash value. The unambiguous version of this document is: sha1:{{ site.github.build_revision }}

Introduction
------------

*Content-based Versioning* is a methodology of Versioning that identifies *a specific manifestation of bits*. Whether it be a document, an executable, a package, a system, a hardware schematic or so much more. A *version* of that asset is the unambiguous identification of that exact asset.

Label-based Versioning does not scale well in an agile and experimentative world. It leads to confusion and conflict. The ability to name things accurately, reliably, consistently and in a manner that anyone else can verify that they are looking at exactly what you meant them to look at (non-repudiability) is an essential tool in the agile security sandbox.

Content Versioning has many distinct advantages over label-based versioning. First and foremost, you are not required to maintain a correlation table that ties a particular label, to a particular asset. With that 

Why Linear Versioning is insufficient
---------------------------------------

In the modern world of agile development, progress is not linear in nature. Things don't progress in an incremental fashion, and an incremental release does not indicate progress. Innovation happens through forks, branches, rewrites, and experiments. It truly is, and therefore mimics biological evolution. New adaptations happen, sometimes adaptations fork off and become new things entirely. Sometimes different branches merge. Some lineages simply die out and go extinct.

We therefore believe that versioning these innovations on a linear scale leads to a great deal of confusion, conflict and awkward workarounds when releasing from different branches, or when releasing from different repositories. Furthermore, when taking dependencies, a "version" is a fairly broad stroke to determine based on. For example, when a breaking change happens across versions, it rarely is breaking for all consumers. Alternately, a non-interface change that doesn't break interfaces, but breaks behavior, can easily be a breaking change for some consumers.

In practice, versioning merely becomes a discriminant, to discriminate between two manifestations of a component. It is pragmatically no different than assigning a monotonically increasing timestamp.

Why Use Content Versioning?
----------------------------


FAQ
---

### How do I determine which version comes first?


About
-----

The Content Versioning specification is authored and sponsored by [Polyverse Corporation](https://polyverse.io).

If you'd like to leave feedback, please [open an issue on
GitHub](https://github.com/polyverse-security/contentversioning/issues).


License
-------

Creative Commons - CC BY 3.0
http://creativecommons.org/licenses/by/3.0/
