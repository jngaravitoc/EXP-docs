.. _topics-contributing:

===================
Contributing to EXP
===================

.. important::

   If you are using the ``EXP-code/docs`` repo to build a local copy
   of the documentation, please double check that you are reading the
   most recent version of this document by issuing a ``git pull``.

There are many ways to contribute to EXP. Here are some of them:

* Blog about EXP. Cite the EXP published papers. Tell the world how
  you're using EXP. This will help newcomers with more examples and
  will help the EXP project to increase its visibility.

* Report bugs and request features in the `issue tracker`_, trying to follow
  the guidelines detailed in `Reporting bugs`_ below.

* Submit new examples to the `EXP examples repo
  <https://github.com/EXP-code/EXP-examples>`_ or the 
  `pyEXP examples repo
  <https://github.com/EXP-code/pyEXP-examples>`_.   See the
  :ref:`writing-examples` section.


Stable and development branches
===============================

Our current branch policy changed as of May 1, 2023.  Rather than a
_static_ ``main`` branch for a stable EXP/pyEXP release with
_development_ taking place on the ``devel`` branch, the only official
EXP branch will be ``main``.  All development will take place through
a `pull request`_ to ``main``.  All other branches are considered to be
temporary.  The current stable release will be tagged in the GitHub
release menu.   The HEAD of ``main`` will contain the latest new
features and fixes.  


Reporting bugs
==============

Well-written bug reports are very helpful, so keep in mind the following
guidelines when you're going to report a new bug.

* check the :ref:`FAQ <faq>` first to see if your issue is addressed in a
  well-known question

* check the `open issues`_ to see if the issue has already been reported. If it
  has, don't dismiss the report, but check the ticket history and comments. If 
  you have additional useful information, please leave a comment, or consider
  :ref:`sending a pull request <code-development>` with a fix.

* write **complete, reproducible, specific bug reports**. The smaller
  the test case, the better. Remember that other developers won't have
  your project to reproduce the bug, so please include all relevant
  files required to reproduce it.

* the most awesome way to provide a complete reproducible example is
  to send a pull request which adds a failing test case to the EXP
  testing suite (see :ref:`submitting-patches`).  This is helpful even
  if you don't have an intention to fix the issue yourselves.

* include the output of ``exp -v`` so developers working on your bug
  know exactly which version and platform it occurred on, which is
  often very helpful for reproducing it, or knowing if it was already
  fixed.

.. _code-development:

Contributing to code development
================================

We are now using the `pull request`_ method for all EXP development,
in including the code authors and maintainers.  In essence, a pull
request is code patch that allows us to easily review, test, and
discuss the proposed change.  The better a patch is written, the
higher the chances that it'll get accepted and the sooner it will be
merged.

Well-written patches should:

* contain the minimum amount of code required for the specific change. Small
  patches are easier to review and merge. So, if you're doing more than one
  change (or bug fix), please consider submitting one patch per change. Do not
  collapse multiple changes into a single patch. For big changes consider using
  a patch queue.

* pass all EXP basic example tests. See `Running tests`_ below.

* if you're contributing a feature, especially one that changes a
  public (documented) API, please include the documentation changes in
  the same patch.  See `Documentation strategy`_ below.

.. _submitting-patches:

Submitting patches
==================

The best way to submit a patch is to issue a `pull request`_ on
GitHub.  The work flow for this is:
1. Fork the ``EXP-code/EXP`` repo in GitHub
2. Create a branch with the proposed change
3. Compile and test your changes
4. Once you are satisfied, create the `pull request`_ on the GitHub EXP code repo

Remember to explain what was fixed or the new functionality (what it
is, why it's needed, etc). The more info you include, the easier will
be for core developers to understand and accept your patch.

You can also discuss the new functionality (or bug fix) before
creating the patch, but it's always good to have a patch ready to
illustrate your arguments and show that you have put some additional
thought into the subject. A good starting point is to send a pull
request on GitHub. It can be simple enough to illustrate your idea,
and leave documentation/tests for later, after the idea has been
validated and proven useful.  All functionality (including new
features and bug fixes) must include a test case to check that it
works as expected, so please include tests for your patches if you
want them to get accepted sooner.

There might be an existing pull request for the problem you'd like to
solve, so please do take a look at the existing pull request list.
For example, a pull request might be a good start, but changes are
requested by EXP maintainers, and the original pull request author
hasn't had time to address them.  In this case consider picking up
this pull request: open a new pull request with all commits from the
original pull request, as well as additional changes to address the
raised issues. Doing so helps us a lot; it is not considered rude as
long as the original author is acknowledged by keeping his/her
commits.

You can pull an existing pull request to a local branch by running
``git fetch upstream pull/$PR_NUMBER/head:$BRANCH_NAME_TO_CREATE``
(replace 'upstream' with a remote name for scrapy repository,
``$PR_NUMBER`` with an ID of the pull request, and
``$BRANCH_NAME_TO_CREATE`` with a name of the branch you want to
create locally).  See also:
https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/checking-out-pull-requests-locally#modifying-an-inactive-pull-request-locally.

When writing GitHub pull requests, try to keep titles short but
descriptive.  Complete titles make it easy to skim through the issue
tracker.

Finally, we all appreciate improving the code's readability and though
formatting and improved comments.  But please, try to keep aesthetic
changes in separate commits from functional changes. This will make
pull requests easier to review and more likely to get merged.


.. _documentation-strategy:

Documentation strategy
======================

EXP and pyEXP has three types of documentation:

1. Inline Doxygen comments in C/C++ class headers.  If you have not
   used `Doxgyen <http://doxygen.org>` in the past, we recommend that
   you simply copy the style in existing headers in the ``include``
   directory in the EXP source tree.  In short, Doxygen uses stylized
   comments to extract documentation.  Lines that start with ``//!``
   or blocks that start with ``/**`` and end with ``*/`` will end up
   describing the immediately following class or member function.

2. Python wrapper code has embedded Python docstrings.  For some
   examples, check the C++ code in the ``pyEXP``.

3. The ReadTheDocs manual that you are currently reading is designed
   to provide an overview and tutorial for using EXP/pyEXP.  You can
   fork and issue pull requests against the ``EXP-code/docs`` repo
   just for the EXP source code as described in :ref:`submitting-patches`.

.. _writing-examples:

Writing examples
================

We strongly encourage to contribute interesting examples and workflows
to one of the two example repositories:

1. Use the `EXP examples repo
   <https://github.com/EXP-code/EXP-examples>`_ to illustrate
   simulations.  Check the existing ones for guidance. It's best if
   your examples contain sample configuration files and phase-space
   files, or possibly instructions for computing the phase-space files
   if they are large.

2. Use the `pyEXP examples repo
   <https://github.com/EXP-code/pyEXP-examples>`_.  Either documented
   Python or Jupyter notebooks are ideal.
   
.. _running-tests:

Running tests
=============

Please check any bug fixes and proposed new functionality works with
existing examples.  Here are some suggested guidelines for EXP and
pyEXP changes, respectively:

1. For EXP, clone the `EXP examples repo
   <https://github.com/EXP-code/EXP-examples>`_ to test changes to the
   EXP simulation code.  At the very least, please try the ``Better``
   example, but please try as many as you can to make sure that your
   change will not break an existing use case for someone else.  If
   your change introduces a feature, please try to devise and
   contribute example that demonstrates the new feature.  That way,
   your new feature will be tested by all future proposed changes and
   will help others understand how to use your new feature.

2. The drill for pyEXP is similar.  Clone `pyEXP examples repo
   <https://github.com/EXP-code/pyEXP-examples>`_ to test changes to
   the pyEXP N-body analysis code. There are many work flows here, we
   don't expect anyone to try all of them.  But please use your best
   judgment to try those affected by your proposed change.

.. _issue tracker: https://github.com/scrapy/scrapy/issues
.. _tests/: https://github.com/scrapy/scrapy/tree/master/tests
.. _open issues: https://github.com/scrapy/scrapy/issues
.. _pull request: https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request
