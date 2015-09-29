===============================
git-repo-manifests
===============================

git-repo-manifests
==================

git-repo-manifests is a collection of manifest files that are used with
Google's git-repo program


Installing the repo script
--------------------------

Instructions for installing the repo script are at:

https://source.android.com/source/downloading.html

In the section **'Installing Repo'**


Configure gitconfig
-------------------

In your ``~/.gitconfig`` you need to add a section like this. Please make sure
to put your actual Gerrit ID where it says ``YOUR_GERRIT_ID_HERE``::

  [review "https://review.openstack.org/"]
      username = YOUR_GERRIT_ID_HERE


Sample usage
------------

::

  $ mkdir ironic-repo
  $ cd ironic-repo
  $ repo init -u https://git.openstack.org/openstack/git-repo-manifests -m ironic
  $ repo sync --no-clone-bundle
  $ cd ironic
  $ repo start testing ironic
  $ touch ironic/tests/TESTING
  $ git add ironic/tests/TESTING
  $ git commit -m 'Testing'
  $ repo upload ironic
