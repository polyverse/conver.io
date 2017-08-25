Content-based Versioning {{ site.github.build_revision }}
==============================

Summary
-------

Given a digital asset (source code, binaries, groups of files, images, videos, etc.), run a cryptographically-secure hash over the bits that comprise that asset, and use the hash as the version for that asset.
1. Identify exactly what comprises "an asset". It may be convenient, though not necessary, to tar/zip a group of files together.
2. Pick a currently-known cryptographically-secure Hash function. For example SHA256, as of the time this was last versioned @{{ site.github.build_revision }}
3. Use this hash as the version of that asset. The version of this document is: {{ site.github.build_revision }}
4. Optionally, to avoid ambiguity, prefix the hash function name, separated by a colon, behind the hash value. The unambiguous version of this document is: sha1:{{ site.github.build_revision }}

Introduction
------------



Content Versioning Specification (ConVer)
------------------------------------------


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
