# revert vs reset vs restore

**git revert <commit>** creates a new commit that undoes the changes from an
earlier commit. History is preserved. This is the safe option on any branch
that has been pushed or that other people use.

**git reset <commit>** moves the current branch pointer backward.
--soft keeps the changes staged, --mixed (default) keeps them in the working
directory unstaged, and --hard discards them entirely. It rewrites history,
so it is only safe on commits you have not pushed.

**git restore <file>** discards uncommitted changes in the working directory,
or unstages a file with --staged. It does not touch commit history at all.

Rule of thumb: revert for pushed commits, reset for local commits, restore for
uncommitted file changes.
