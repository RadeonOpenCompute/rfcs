
# RFCs for changes Requests for ROCm

## ROCm RFC Process
[ROCm RFCs]: #ROCm-rfcs

Many changes, including bug fixes and documentation improvements can be
implemented and reviewed via the normal GitHub pull request workflow.

Some changes though are "substantial", and we may ask that these be put through a
bit of a design process and produce a consensus among the ROCm community and
the AMD Core Developers.

The "RFC" (request for comments) process is intended to provide a consistent
and controlled path for new features to enter the language and standard
libraries, so that all stakeholders can be confident about the direction the
language is evolving in.


## Table of Contents
[Table of Contents]: #table-of-contents

  - [Opening](#ROCm-rfcs)
  - [Table of Contents]
  - [When you need to follow this process]
  - [What is the process]
  - [The RFC life-cycle]
  - [Reviewing RFCs]


## When you need to follow this process
[When you need to follow this process]: #when-you-need-to-follow-this-process

You need to follow this process if you intend to make "substantial" changes to
ROCm Core Technology, Tools, Libraries, or the RFC process itself. What constitutes a
"substantial" change is evolving based on community norms and varies depending
on what part of the ecosystem you are proposing to change, but may include the
following.

  - Any semantic or syntactic change to the language that is not a bugfix.
  - Removing language features, including those that are feature-gated.
  - Changes to the interface between the compiler and libraries, including lang
    items and intrinsics.
  - Additions to `std`.

Some changes do not require an RFC:

  - Rephrasing, reorganizing, refactoring, or otherwise "changing shape does
    not change meaning".
  - Additions that strictly improve objective, numerical quality criteria
    (warning removal, speedup, better platform coverage, more parallelism, trap
    more errors, etc.)
  - Additions only likely to be _noticed by_ other developers-of-ROCm,
    invisible to users-of-ROCm.

If you submit a pull request to implement a new feature without going through
the RFC process, it may be closed with a polite request to submit an RFC first.


## What is the process
[What is the process is]: #what-is-the-process

In short, to get a major feature added to ROCm, one must first get the RFC
merged into the RFC repository as a markdown file. At that point the RFC is
"active" and may be implemented with the goal of eventual inclusion into Rust.

  - Fork the RFC repo [RFC repository]
  - Copy `0000-ROCm-rfc-template.md` to `text/0000-ROCm-rfc-template.md` (where "my-feature" is
    descriptive. don't assign an RFC number yet).
  - Fill in the RFC. Put care into the details.
  - Submit a pull request. As a pull request the RFC will receive design
    feedback from the larger community, and the author should be prepared to
    revise it in response.
  - Each pull request will be labeled with the most relevant team, which
    will lead to its being triaged by that team in a future meeting and assigned
    to a member of the ROCm team.
  - Build consensus and integrate feedback. RFCs that have broad support are
    much more likely to make progress than those that don't receive any
    comments. Feel free to reach out to the RFC assignee in particular to get
    help identifying stakeholders and obstacles.
  - There will be discussion on the RFC pull request, as much as possible will be in
    comment thread of the pull request itself. Offline discussion will be
    summarized on the pull request comment thread.
  - At some point, a member of the team will propose a "motion for final
    comment period" (FCP), along with a *disposition* for the RFC (merge, close,
    or postpone).
    - This step is taken when enough of the tradeoffs have been discussed that
    the subteam is in a position to make a decision. That does not require
    consensus amongst all participants in the RFC thread (which is usually
    impossible). However, the argument supporting the disposition on the RFC
    needs to have already been clearly articulated, and there should not be a
    strong consensus *against* that position outside of the subteam. Subteam
    members use their best judgment in taking this step, and the FCP itself
    ensures there is ample time and notification for stakeholders to push back
    if it is made prematurely.
  

## The RFC life-cycle
[The RFC life-cycle]: #the-rfc-life-cycle

Once an RFC becomes "active" then authors may implement it and submit the
feature as a pull request to the Rust repo. Being "active" is not a rubber
stamp, and in particular still does not mean the feature will ultimately be
merged; it does mean that in principle all the major stakeholders have agreed
to the feature and are amenable to merging it.

Furthermore, the fact that a given RFC has been accepted and is "active"
implies nothing about what priority is assigned to its implementation, nor does
it imply anything about whether a Rust developer has been assigned the task of
implementing the feature. While it is not *necessary* that the author of the
RFC also write the implementation, it is by far the most effective way to see
an RFC through to completion: authors should not expect that other project
developers will take on responsibility for implementing their accepted feature.

Modifications to "active" RFCs can be done in follow-up pull requests. We
strive to write each RFC in a manner that it will reflect the final design of
the feature; but the nature of the process means that we cannot expect every
merged RFC to actually reflect what the end result will be at the time of the
next major release.

In general, once accepted, RFCs should not be substantially changed. Only very
minor changes should be submitted as amendments. More substantial changes
should be new RFCs, with a note added to the original RFC. Exactly what counts
as a "very minor change" is up to the sub-team to decide; check
[Sub-team specific guidelines] for more details.


## Reviewing RFCs
[Reviewing RFCs]: #reviewing-rfcs

While the RFC pull request is up, the team member may schedule meetings with the
author and/or relevant stakeholders to discuss the issues in greater detail,
and in some cases the topic may be discussed at a sub-team meeting. In either
case a summary from the meeting will be posted back to the RFC pull request.

A team makes final decisions about RFCs after the benefits and drawbacks
are well understood. These decisions can be made at any time, but the team
will regularly issue decisions. When a decision is made, the RFC pull request
will either be merged or closed. In either case, if the reasoning is not clear
from the discussion in thread, the team will add a comment describing the
rationale for the decision.


