===================================
 Working with Branches and Patches
===================================

Working on `OpenStack <https://openstack.org>`_ means that you
typically will be using some combination of upstream code along with
your own customizations. These might be plugins, extra requirements
and everything in between. But, no matter what you do, you'll want to
keep everything automated.

This repo outlines some strategies for handling this process of
keeping up with upstream while maintaining your own org specific
patches.


Using Branches and Merges
=========================

One ides is to use some long lived branches that are constantly merged
into the "release" branch. The idea is that you merge "upstream" and
then merge your "org" branch to create a new release head.

Terms
-----

 - "upstream" - The project's primary tracking repo. For example,
   https://github.com/openstack/designate

 - "org" - The organizations specific packages. Pull requests and
   feature branches for org specific features would go here.

 - "release" - This is typically "master". This is our target for
   merging changes for release.


Assumptions
-----------

 - upstream is merged into the release branch on a cadence
 - org is rebased on release branch on a cadence
 - features branched from org are consistently rebased against org


Process
-------

Here is the process to getting a repo ready for building an artifact.

::

   $ git checkout master
   $ git merge upstream
   $ git merge org
   $ git tag $release
