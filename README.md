
I like keeping my papers under git version control. **Problem:** my supervisor
does not use Git, he just wants to read a PDF and make some changes in the
text. I want to share the paper via Dropbox but I also want to keep my git repo
under Dropbox, and I certainly don't want to go around doing an intricate dance
of copying around folders.

To get started:

1. create a git repository with your paper, and commit
2. `dropbox-paper init ~/Dropbbox/CureForCancerPaper` this will clone the repo
   into your Dropbox, and setup a workcopy branch in the Dropbox folder, the remote
   repo is named dropbox-paper

It is perfectly safe to `git push dropbox-paper master` this will not alter the
workcopy in the Dropbox folder, only the .git folder.  Better yet you can call
`dropbox-paper push` as this will push your changes, and update the workcopy -
but only if it was not changed.

`dropbox-paper status` shows information about the workcopy status, and dropbox sync.

The folder in Dropbox is just another repo, but the checked out branch is not
the *master* branch, instead it is called *workcopy*. This avoids issues when
a push is done into dropbox.

`dropbox-paper push` will try a clean fast-forward merge if there are no changes
in the working copy in Dropbox. If there are changes it will just print a message.




