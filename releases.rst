.. _releases:

Release process
===============

.. note::
   In this section you will learn how releases work in a general way at
   Sourcefabric. Be aware this may vary from one product to another to
   suit particular needs.

Official versions
-----------------

An official version is a version of the product that has been publicly released.
There are three different types of versions depending on the magnitude and
characteristics of the changes: *grand*, *major* and *minor*.

*Grand releases* happen very infrequently, and in most of the cases represent
large, sweeping changes to the product.

*Major releases* happen in general every few months, this is product specific
though as each product has its own roadmap. A major release will include usually
new features, improvements to existing features, and such, together with a set
of bug fixes.

*Minor releases* (a.k.a. maintenance releases) happen at least once between
major releases, and probably more often if required. Minor releases will be
100% compatible with the associated major release. A minor release includes
only localization updates, bug and security fixes.

.. _versioning:

Version numbering
~~~~~~~~~~~~~~~~~

Sourcefabric products which define an API from their very first version follow
the *semantic versioning* convention (e.g. Liveblog, Superdesk.)

.. note::Semantic versioning
   The *Semantic Versioning* specification can be found at http://semver.org.

Other Sourcefabric products (e.g. Airtime, Booktype, Newscoop) use the following
numbering conventions for releases:

- Versions are numbered in the form A.B or A.B.C.
- Grand releases follows the convention A.B, where B is always a zero (e.g. 1.0,
  5.0, etc.)
- Major releases follows the convention A.B, where B has always a positive value
  that increments by 1 (e.g. 4.1, 4.2, etc.)
- Minor releases follows the convention A.B.C (e.g. 1.5.2, 1.5.3, etc.)
- *A* represents the grand version number, which is only incremented for dramatic
  changes to the product, and these changes are not necessarily
  backward-compatible. That means, for example, code you wrote for Airtime 2.1
  may break when we release Airtime 3.0.
- *B* represents the major version number, which is incremented for major yet
  backward-compatible changes. Using the same example; code written for Airtime
  2.1 will continue working under Airtime 2.2. Exceptions to this rule may occur
  and will be accordingly documented in the release notes.
- *C* is the minor version number, which is incremented for bug and security
  fixes. A new minor release will be 100% backward-compatible with the previous
  minor release.

In some cases, we make alpha, beta, or release candidate releases. These are of
the form A.B-[alpha/beta/rc]N, which means the Nth alpha/beta/release-candidate
of version A.B.

Supported versions
------------------

Supported versions refer always only to major versions, e.g. Newscoop supported
versions (at the moment of writing this): 4.0, 4.1 and 4.2.


