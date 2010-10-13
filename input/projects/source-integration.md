title: MantisBT Source Integration
menu-parent: 51
menu-position: 511
menu-title: Source Integration
---

My premiere plugin set, this package provides a generalized framework for integrating source control
repositories within the normal MantisBT workflow.  Building on that framework are a set of integration
plugins that implement individual VCS tools, and translate that data into the framework's generalized
data types.  Once translated, the framework can act on those datasets in many ways to improve the workflow
in MantisBT, or to better inform developers and team members when looking at issues.

Some of the unique features offered by this framework include the ability to link changesets to issues and
the users that created them, automatic resolving or manipulation of issues depending on commit messages, and
the ability to intelligently map repository branches to project versions in the tracker.  For instance, when
I commit a bugfix to the MantisBT repository's "master" branch, if the commit message says "Fixes issue #17",
the tracker can automatically mark issue #17's fixed-in version as "1.3.x", the current development version.
Once repository and commit data has been imported into MantisBT, it can be browsed or searched, and each
changeset can automatically link the user to external diffing or viewing tools appropriate for that
repository and tool.

But the best part about this framework is that it inherently supports the fundamental concepts behind *any*
version control tool.  While it currently includes Git and Subversion with the core framework, it can just as
easily support integration for other tools, including Mercurial, CVS, or Bazaar.  All it requires is a
developer knowledgeable in that version control tool to write a simple integration layer, and indeed there
is already an integration layer in the works for both Mercurial and Perforce.

This framework can be seen in use on the official [MantisBT][] tracker, as well as on my own [bugtracker][].
The source code can be found on [MantisForge][] or cloned from the [Source Integration repo][sourcerepo].

{%
posts = pagelist(key=lambda p: "tags" in p and "source integration" in tagsplit.findall(p.tags), sortby=lambda p: p.get("date"), reverse=True)
for p in posts:
	inline(p)
%}

[mantisbt]: http://www.mantisbt.org/ "Mantis Bug Tracker"
[mantisforge]: http://git.mantisforge.org/ "MantisForge"
[bugtracker]: http://leetcode.net/mantis/ "LeetCode.net Bugtracker"
[sourcerepo]: git://git.mantisforge.org/source-integration.git "Source Integration Repository"
