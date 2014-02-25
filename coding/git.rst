.. _git:

Git and GitHub Pull Requests
============================

Here you will learn how to contribute code to any of the Sourcefabric products.
The short version is: do it via GitHub Pull Requests.

In the Sourcefabric Development Team we use Git as the revision control system
and source code management tool, and GitHub to manage the code committing cycle
for all Sourcefabric Products.

.. note::
   This page is not intended as a GitHub guide. GitHub provides already a fairly
   good bit of help that you can always consult.

We are glad to receive your contributions in some other ways, especially if you
have decided not to be a GitHub user. Submitting GitHub Pull Requests though
makes the job of the core developers a lot easier, for example when reviewing
the code, and increases the likelihood of getting your contribution merged into
our products.

Installing and Setting up Git
-----------------------------

You can download Git and get it installed, but you better do that with the help
of your Operating System's software manager, it is always easier (wink)

Once you have installed Git, the first thing to do is to tell Git about your
name and e-mail address.

    $ git config --global user.name "Your name"
    $ git config --global user.email "your.email@example.com"

Set user.name to your real name, not your GitHub nick or any other nick name.

The email address you set for user.email must match your registered address in
GitHub, as this will be used to associate your commits with your GitHub account.

Getting ready
-------------

Before writing your code you must have setup your work environment. This is done
in three simple steps.

Let's assume your GitHub account is johndoe, and that the Sourcefabric project
you want to contribute to is Superdesk.

The first thing to do is to fork the Superdesk repository in GitHub, so:

- Login in your GitHub account
- Go to the Superdesk project space in GitHub
- Look for the button labelled Fork and click on it

You have now in your GitHub account a replica of the Superdesk repository, that
is your fork and lives only in GitHub.

Now you need to download the source code so that you can work locally in your
own computer. Open a console and type in this:

    $ git clone git@github.com:johndoe/Superdesk.git

This will create a new directory Superdesk in your current working directory
containing a clone of your GitHub repository. This clone has by default a single
remote called origin, that points to your fork on GitHub.

Your local copy of the Superdesk project is tracking your GitHub fork, but what
about the original Sourcefabric repository? It is really important to track the
original project, otherwise you wouldn't get the updates from all the other
developers that get merged into upstream.

    $ git remote add upstream https://github.com/sourcefabric/Superdesk.git
    $ git fetch upstream

The new remote is called, in this case, upstream. You can call it anyway you
want, we call it upstream because that's what it is, plus it is a common
practice to use that name.

Working on a ticket
-------------------

Create a new branch any time you will start working on a ticket, and create it
branching off of upstream/master.

    $ git checkout -b ticket-xxxxx upstream/master

You can also create a branch based on a different branch than master, for
example when working on a bug fix for a release branch, let's say 1.2

    $ git checkout -b ticket-xxxxx-1.2 upstream/1.2

Do your work and commit to your local branch (remember to follow the
<conventions on commit messages>, that is a great help for core developers when
reviewing your code) and push your changes to your fork in GitHub.

    $ git push origin ticket-xxxxx

The first time you run this command you will notice in your GitHub fork that a
new branch has been created. From then on you can use the same command to
update your branch with new commits.

Pushing your stuff to GitHub
----------------------------

When you consider you are done with the task...

