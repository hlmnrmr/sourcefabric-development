.. _git:

Git repositories
================

Whenever you want to work with any of our products either for trying
in-development features or contributing to development, you will need to get a
copy of the source code. You do so by cloning the corresponding Git repository.
Here you will find all the necessary information on how the Git repositories
are organized, so you know where to look for stuff.

.. admonition:: Usage in production

   If rather what you want to do is to setup and deploy a system to run in a
   production environment we highly recommend getting an official release
   package. The source code as it is in the Git repositories goes always through
   a building phase that prepares it to run as expected. We cannot guarantee the
   same results otherwise.

The short version
-----------------

In Sourcefabric we use Git as management system for the source code. You can
find all official Git repositories hosted in GitHub at
`https://github.com/sourcefabric/ <https://github.com/sourcefabric/>`_.

The branching model we follow in Sourcefabric aims simplicity. It considers
three different types of branches:

* main development branch (a.k.a. master): the base for almost all development.
  Every time you will start working on something new, you should do it based on
  master.
* release branches: officially supported versions of the product are kept in
  release branches, this is mainly for maintenance. If you want to contribute a
  fix to a bug that affects any of the supported released versions, you should
  do it against the corresponding release branch.
* feature branches: when a new major feature or improvement is being done,
  likely work happens in a feature branch to not affect master directly.

Every release can be found in our repositories in the form of Git tags.

If you find this short version not enough to understand the model, please keep
reading.

Branches in detail
------------------

The master branch
`````````````````

* master is the main development branch. This is the code to base new features,
major improvements and re-factoring on. It holds the code that will constitute
the next grand or major release.

* master, being the main development branch, is the only one permanent branch in
the repository, it will be always available and won't be never removed. All
other branches have a lifetime, they are created and deleted when not needed
anymore.

* master is an active development branch, therefore it is not considered to be
in a stable state.

* However, supported in our development workflow, master can be considered to
be always in a good functional state.

* master triggers either a grand release or a major release, only.

Release branches
````````````````

These are development branches for the officially supported versions of the
products.

* Every officially supported version of a product has a corresponding release
  branch.

* Lifetime of a release branch is determined depending on whether the version
  is officially supported or not. When a released version is not officially
  supported anymore, the corresponding release branch is removed from the
  repository.

* Bug fixing usually happens here, and then --if apply- the fix is ported to
  master. It can also be done the other way around, important is to make sure
  that the fix will be available for all affected branches.

* NO new features are ever added to a release branch.

* A release branch triggers always and in all cases the next minor release,
  only.

* Whenever a release needs to happen, a new release branch is created branching
  off master, and when doing so ALL new features added since the last release
  will be part of the new release, this means you cannot cherry pick which
  features will make the new release.

* Branch naming convention: <Version Number>. Where the version number
  corresponds to a minor release (e.g. 1.5, 2.3, 4.1).

Feature branches
```````````````` 

Implementation of new big features, experimenting features, major improvements,
re-factoring and re-writing, are made in separate feature branches.

* Whenever an enhancement is required, it is done in a specific branch,
  branching off master.

* Lifetime of feature branches goes from the moment where the implementation
  begins till the moment when the branch is merged back to master. Once that
  happens the feature branch may be removed from the repository.

* A feature branch never triggers a release. Features are always merged back to
  master in order to be released.

* Branch naming convention: <Jira Ticket Code>-<Short Descriptive Title>, where
  <Short Descriptive Title> must be in lowercases and must use the dash sign “-”
  as word separator (e.g. cs-2764-autosave).

Released Versions
-----------------

Officially released versions are available in the form of Git tags. Every time a
new version is released, a new Git tag is created, using the following naming
convention:

v<Version Number> (e.g. v4.0.0, v2.1.1-RC2)

You can see the list of released tags by checking:
`https://github.com/sourcefabric/[product]/tags
<https://github.com/sourcefabric/[product]/tags>`_

