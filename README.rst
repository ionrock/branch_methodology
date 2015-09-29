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


The org branch needs needs to be constantly rebased on top of master,
which should be getting merged with upstream on a cadence.
