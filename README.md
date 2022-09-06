# Overview

*This is a private repo. It is currently only accessible to the Documentation
team. We might want to move a lot of the below words to the [Technical Author
Handbook][].*

This place is a first attempt at centrally managing documentation reviews. It
is primarily useful for those projects that are not under version control
(currently the vast majority of them).

## Submitting a PR

Submit a PR when you want something reviewed.

The PR can consist of:

  - an actual file in any format (e.g. Text, Markdown, reStructuredText)
  - a link to external content, such as:
    - Google doc
    - published page
    - Discourse topic

### Description

The PR description should include guidelines for the prospective reviewer such
as:

  - general review
  - structure
  - language
  - technical
  - point to a specific portion of the content

### Contents

Add the PR file under the appropriate project directory.

If the PR consists of multiple files, add a subdirectory.

## Reviewing a PR

Any doc team member can review a PR, but starting a review does not sign you up
for its eventual approval. Just leave any comments you may have.

## Approving a PR

An approval/merge signals that the content is good for public consumption.
Hence, only approve if your confidence is high.

Once approved, it is up to the requester to ensure that the content gets
published in the correct format and in its rightful place. If a Google doc was
used, it would be smart to leave a note in that doc for any future travellers
(e.g. "This page is deprecated. Its contents was reviewed by the Doc team and
approved on $DATE.").

## Stretch goals and ideas:

 - Have a bot send notifications to the [Documentation authors][] Mattermost
   channel when there are reviews waiting.

<!-- LINKS -->

[Technical Author Handbook]: https://github.com/canonical/technical-author-handbook
[Documentation authors]: https://chat.canonical.com/canonical/channels/documentation-authors
