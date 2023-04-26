# Overview

This repository is leveraged in some non-traditional ways in order to satisfy
specific use cases involving Canonical product documentation.

It acts as a communication channel and tracking system. It does not impose a
change on how Canonical teams work in terms of documentation. Instead, it adds
extra capabilities that teams can optionally take advantage of.

# Use cases

The doc-hub can be used to:

* track content requests or content additions
* provide traditional content reviews
* relocate existing company knowledge

The doc-hub would primarily be useful in a Discourse context, where these use
cases are difficult, if not impossible, to satisfy.

# Documentation defined

Some products leverage upstream projects, notably Charmed Kubernetes and
Charmed OpenStack. Documentation as discussed in the context of this repository
is both product-specific and generic.

## product-specific

Content that is:

* concerned with deploying and managing services/applications with charms or
  snaps
* not of a pure upstream nature

## generic

Content that is:

* fit for general consumption
* not associated with:
    * technical corner cases or environment-specific situations
    * a condition arising from a specific combination of versions in a software
      stack

# Workflows

Workflows for the aforementioned use cases are now described.

When a workflow involves the opening of a PR (pull request), the requester
should create an appropriately named (descriptive) sub-directory under a
pre-existing directory that corresponds to the related technology:

     doc-hub
       └── openstack
             └── traffic-flows-openstack-neutron

## Track content requests or content additions

Any perceived missing subject matter is recorded as an issue. These requests
(or contributions) would typically involve the creation of a new page of
documentation. Calling out mistakes or desired enhancements in existing content
should probably be done on the corresponding Discourse forum topic.

To expedite the publication of the new content, the requester (or contributor)
should supply as much supporting information as possible. The
requester/contributor also tacitly agrees to act as contact person should any
new questions arise during the content creation process and will be asked to
verify the finalised content.

**Workflow:**

1. user files an issue
1. labels applied: <related-tech>
1. TA assigned
1. questions asked, issue understood
1. labels applied: request triaged (or contribution triaged)
1. content published, issue closed

## Provide traditional reviews

Content can be submitted, including by TAs themselves, as a pull request (PR)
in order to receive a traditional content review. The requester will be
responsible for responding to any review commentary and enhancing the content
as required. They will also be in charge of moving the reviewed content to its
rightful place for publication purposes.

The PR description should include guidelines for the prospective reviewer in
cases where a specific kind of review is being sought, such as:

* general review
* structure
* language
* format
* point to a specific portion of the content

The review process is format-agnostic (e.g. text, Markdown, RST).

**Workflow:**

1. requester opens a PR
1. labels applied: <related-tech>
1. TA assigned
1. review occurs, PR merged
1. requester assumes responsibility for content

## Relocate existing knowledge

There may be content stored in a team's local knowledge management system that
may actually be better suited for product documentation (e.g. Support team's KB
and the BootStack team's Playbooks).

This can also help avoid duplicated documentation efforts (e.g. same content in
multiple places) as well as provide product documentation with practical
content from teams that interface closely with customers.

**Workflow:**

1. requester opens a PR
1. labels applied: <related-tech> and relocate
1. TA assigned
1. review occurs
1. relocation happens, PR merged

# For Technical Authors

## Reviewing a PR

Any TA can review a PR, but starting a review does not sign you up for its
eventual approval. Just leave any comments you may have.

## Approving a PR

An approval/merge signals that the content is good for public consumption.
Hence, only approve if your confidence is high.
