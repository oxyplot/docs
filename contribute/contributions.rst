=================
How to contribute
=================

.. note:: This section is under construction. Please contribute!


Introduction
------------

Contributions to OxyPlot, whether new features or bug fixes, are deeply appreciated and benefit the whole user community.

The following guidelines help ensure the smooth running of the project, and keep a consistent standard across the codebase. They are guidelines only - should you feel a need to deviate from them it is probably for a good reason - but please adhere to them as closely as possible.


Making contributions
--------------------

If you would like to contribute code or documentation to OxyPlot, we welcome pull requests. 

New features and bugs should always be added in the `issue tracker`_. It might be a good idea to discuss in the forum_ first if you are not sure if it is a bug or a feature we want to include in the library.


License
-------

See the :doc:`../introduction/license` page. Your contributions must be your own work and licensed under the same terms as OxyPlot.

Branches
--------

The repository contains two branches:

- ``master`` - the release branch (stable channel)  
- ``develop`` -  the main branch with the latest development changes (pre-release channel)

See `A successful git branching model`_ for more information about the branching model in use.


Process
-------

1. Search the `issue tracker`_ to see if the bug or new feature is already there.
2. If not, create a new issue
3. Wait for the issue to be tagged
4. Create a fork, branch, do the changes, commit, rebase, push
5. Create a pull request

The changes will be reviewed and merged into the origin_ if everything is OK.


Working with Git
----------------

1. Log in to GitHub and open the origin_ repository. Click the "Fork" button to create your own fork of the repository.
2. Create a clone on your local system: ``git clone https://github.com/yourusername/oxyplot.git``
3. Create a branch for the bugfix/feature you want to work on: ``git branch bugfix-some-error``
4. Checkout the branch: ``git checkout bugfix-some-error``
5. Commit your changes: ``git commit -m <msg>``
6. Rebase interactively ("squash") to the latest commit of the origin_
7. Push: ``git push``
8. Open the GitHub page for your fork and create a "Pull Request"
9. Include the issue number in the pull request comment (not in the title where it will not be linked!)


Commit messages
---------------

Please follow the style of the other messages in the commit history. Explain the intentions for the change and include the issue number.


Requirements for pull requests
------------------------------

- The pull request should be based on the latest commit on the ``develop`` branch of the OxyPlot origin repository
- Include examples or unit tests for the change / new feature
- Update the CHANGELOG.md file
- Make sure the code builds
- Make sure all unit tests are passing
- Follow the :doc:`coding-style`, make sure there are no StyleCop issues
- squash_ each logical change to a single commit 

And please:

- create a branch/pull request for each issue, do not combine multiple issues
- define full name and e-mail address in the change list user information
- update the AUTHORS and CONTRIBUTORS files if you are not already listed there
- include the issue number in the commit message, e.g. "#9945"
- follow the style of the existing commit messages

.. _origin: https://github.com/oxyplot/oxyplot/
.. _issue tracker: https://github.com/oxyplot/oxyplot/issues
.. _forum: http://discussion.oxyplot.org/
.. _squash: http://gitready.com/advanced/2009/02/10/squashing-commits-with-rebase.html
.. _A successful git branching model: http://nvie.com/posts/a-successful-git-branching-model/

..
    http://git-scm.com/book/en/Getting-Started-First-Time-Git-Setup
    http://nvie.com/posts/a-successful-git-branching-model/
    https://wiki.openstack.org/wiki/GitCommitMessages
    http://who-t.blogspot.de/2009/12/on-commit-messages.html