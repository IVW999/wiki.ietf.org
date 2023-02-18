---
title: TracChangeSet
description: 
published: true
date: 2022-12-29T02:35:26.350Z
tags: 
editor: markdown
dateCreated: 2022-12-29T02:35:21.983Z
---

T# rac Changeset Module

Trac has a built-in functionality for visualizing "diffs", or changes to files.

There are different kinds of *change sets*. Some correspond to revisions made in the repositories, others aggregate changes made in several revisions. Ultimately, any kind of difference can be shown.

The changeset view consists of two parts, the *header* and the *diff views*.

## Changeset Header
The header shows an overview of the whole changeset. Here you will find information such as:

- Timestamp — When the changeset was commited
- Author — Who commited the changeset
- Message — A brief description from the author (the commit log message)
- Location — Parent directory of all files affected by this changeset
- Files — A list of files affected by this changeset

If more than one revision is involved in the set of changes being displayed, the *Timestamp*, *Author* and *Message fields* will not be shown.

A colored rectangle indicates how the file is affected by the changeset:

  Green: Added
  Red: Removed
  Yellow: Modified
  Blue: Copied
  Gray: Moved
The color legend is located below the header as a reminder.

## Diff Views
Below the header is the main part of the changeset, the diff view. Each file is shown in a separate section, each of which contains only the regions of the file that are affected by the changeset. There are two different styles to display the diffs: *inline* or *side-by-side*. You can switch between the styles using the preferences form:

- The *inline* style shows the changed regions of a file underneath each other. A region removed from the file will be colored red, an added region will be colored green. If a region was modified, the old version is displayed above the new version. Line numbers indicate the exact position of the change in both the old and the new version of the file.
- The *side-by-side* style shows the old version on the left and the new version on the right and this will typically require more screen width than the inline style. Added and removed regions will be colored in the same way as with the inline style (green and red), and modified regions will have a yellow background.

In addition, various advanced options are available in the preferences form for adjusting the display of the diffs:

- You can set how many lines are displayed before and after every change; if the value all is used, then the full file will be shown.
- You can toggle whether blank lines, case changes and white space changes are ignored, thereby letting you find the functional changes more quickly.
## The Different Ways to Get a Diff
### Examining a Changeset
When viewing a repository check-in, such as when following a changeset [link](/group/rtgwg/TracLink) or a changeset event in the [timeline](/group/rtgwg/TracTimeline), Trac will display the exact changes made by the check-in.

There will be also navigation links to the *Previous Changeset* to and *Next Changeset*.

### Examining Differences Between Revisions
Often you want to look at changes made on a file or on a directory spanning multiple revisions. The easiest way to get there is from the [TracRevisionLog](/group/rtgwg/TracRevisionLog), where you can select the old and the new revisions of the file or directory, and then click the *View changes( button.

### Examining Differences Between Branches
One of the core features of version control systems is the possibility to work simultaneously on different *Lines of Developments*, commonly called "branches". Trac enables you to examine the exact differences between such branches.

Using the **View changes** ... button in the [TracBrowser](/group/rtgwg/TracBrowser) allows you to enter From: and To: path/revision pairs. The resulting set of differences consist of the changes that should be applied to the *From:* content to get to the *To:* content.

For convenience, it is possible to invert the roles of the old and the new path/revision pairs by clicking the *Reverse Diff* link on the changeset page.

### Checking the Last Change
Another way to examine changes is to use the *Last Change* link provided by the [TracBrowser](/group/rtgwg/TracBrowser).

This link will take you to the last change that was made on that path. From there, you can use the *Previous Change* and *Next Change* links to traverse the change history of the file or directory.


----
See also: [TracGuide](/group/rtgwg/TracGuide), [TracBrowser](/group/rtgwg/TracBrowser)

&nbsp;
&nbsp;
&nbsp;

---

*The content of this page was last updated on 2016-05-11. It was migrated from the old Trac wiki on 2022-12-28.*