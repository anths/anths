# Hello, GitHub users.

## GitHub, and it's parent company, Microsoft, continue their work with ICE.

As a community, we should be using other alternatives.
I don't host any of my work here.

(It's also weirdly disapointing how centralized the ecosystem around a
_distributed_ version control system has become.)

[Sourcehut](https://sourcehut.org) is a good alternative which,
in addition to not facilitiating ICE's work,
is more flexible in its services and resists excess centralization.

## Rename your default branch in git.

The default branch name in git, at least as of 2020, is both confusing,
obscuring some of git's properties, and has some racist baggage behind it.
[We should use a different name](http://a.9srv.net/b/master_in_tech),
and git should change the default.
Until git fixes this, you can correct things locally.

### Rename the default branch on a local repository:

This part is trivial:

	git branch -m master main

The fact that it's that simple surprises a lot of people (including me, initially),
because part of the problem is the existing default name hides the fact that
there's nothing special about it.

### Push the new name to any remote/upstream repositories.

If you have remote/upstream repositories, push the new branch out there:

	git push -u origin main

...or whatever your remote repo is, if other than "origin".
You can get a list of your configured upstream repo names with:

	git remote -v

If GitHub is one of your remotes (you are here, after all),
you'll probably want to go to the repository's settings and change the default there.
Once you do this, you'll have both the new and old names in your remote repo.
To delete the old name from your remote repo, so this:

	git push origin --delete master

### Tell git to use better names by default.

To make `git init` create a repo with a better name by default,
add these lines to $HOME/.gitconfig or $HOME/.config/git/config:

	[init]
	     templateDir = ~/.config/git/template/

Then make the template dir with a single line for

	mkdir -p $HOME/.config/git/template
	echo 'ref: refs/heads/main' > $HOME/.config/git/template/HEAD


There's a bit more discussion
[where I got the steps from](https://www.hanselman.com/blog/EasilyRenameYourGitDefaultBranchFromMasterToMain.aspx)
and this linked Stack Overflow note on
[changing the default branch name](https://stackoverflow.com/questions/42871542/how-can-i-create-a-git-repository-with-the-default-branch-name-other-than-maste/50880622#50880622).

Side note: branch names can be unicode.
For example, `git branch -m master 🌱` works fine. :-)


## Find me elsewhere.
You can find me
online at [a.9srv.net](http://a.9srv.net),
in the Fediverse🐘 as [a@pdx.social](https://pdx.social/a),
on Twitter🐦 as [anths](https://twitter.com/anths),
or in the physical world🗺, usually in Columbia County, Oregon.