    XIP: 1
      Title: XIP Purpose and Guidelines
      Status: Draft
      Type: Meta
      Author: Martin Becze <mb@ethereum.org>, Hudson Jameson <hudson@ethereum.org>
      Created: 2015-10-27, 2017-02-01

What is an XIP?
--------------

XIP stands for Expanse Improvement Proposal. An XIP is a design document providing information to the Expanse community, or describing a new feature for Expanse or its processes or environment. The XIP should provide a concise technical specification of the feature and a rationale for the feature. The XIP author is responsible for building consensus within the community and documenting dissenting opinions.

XIP Rational
------------

We intend EXPIPs to be the primary mechanisms for proposing new features, for collecting community input on an issue, and for documenting the design decisions that have gone into Expanse. Because the EXPIPs are maintained as text files in a versioned repository, their revision history is the historical record of the feature proposal.

For Expanse implementers, EXPIPs are a convenient way to track the progress of their implementation. Ideally each implementation maintainer would list the EXPIPs that they have implemented. This will give end users a convenient way to know the current status of a given implementation or library.

XIP Types
---------

There are three types of XIP:

-   A **Standard Track XIP** describes any change that affects most or all Expanse implementations, such as a change to the the network protocol, a change in block or transaction validity rules, proposed application standards/conventions, or any change or addition that affects the interoperability of applications using Expanse. Furthermore Standard EXPIPs can be broken down into the following categories.
    -   **Core** - improvements requiring a consensus fork (e.g. [EXPIP5], [EXPIP101]), as well as changes that are not necessarily consensus critical but may be relevant to “core dev” discussions (for example, [EXPIP90], and the miner/node strategy changes 2, 3, and 4 of [EXPIP86]).
    -   **Networking** - includes improvements around [devp2p] ([EXPIP8]) and [Light Expanse Subprotocol], as well as proposed improvements to network protocol specifications of [whisper] and [swarm].
    -   **Interface** - includes improvements around client [API/RPC] specifications and standards, and also certain language-level standards like method names ([EXPIP59], [EXPIP6]) and [contract ABIs]. The label “interface” aligns with the [interfaces repo] and discussion should primarily occur in that repository before an XIP is submitted to the EXPIPs repository.
    -   **ERC** - application-level standards and conventions, including contract standards such as token standards ([ERC20]), name registries ([ERC26], [ERC137]), URI schemes ([ERC67]), library/package formats ([EXPIP82]), and wallet formats ([EXPIP75], [EXPIP85]).

-   An **Informational XIP** describes a Expanse design issue, or provides general guidelines or information to the Expanse community, but does not propose a new feature. Informational EXPIPs do not necessarily represent Expanse community consensus or a recommendation, so users and implementers are free to ignore Informational EXPIPs or follow their advice.
-   A **Meta XIP** describes a process surrounding Expanse or proposes a change to (or an event in) a process. Process EXPIPs are like Standards Track EXPIPs but apply to areas other than the Expanse protocol itself. They may propose an implementation, but not to Expanse's codebase; they often require community consensus; unlike Informational EXPIPs, they are more than recommendations, and users are typically not free to ignore them. Examples include procedures, guidelines, changes to the decision-making process, and changes to the tools or environment used in Expanse development. Any meta-XIP is also considered a Process XIP.

XIP Work Flow
-------------

The XIP repository Collaborators change the EXPIPs status. Please send all XIP-related email to the XIP Collaborators, which is listed under XIP Editors below. Also see XIP Editor Responsibilities & Workflow.

The XIP process begins with a new idea for Expanse. It is highly recommended that a single XIP contain a single key proposal or new idea. The more focused the XIP, the more successful it tends to be. A change to one client doesn't require an XIP; a change that affects multiple clients, or defines a standard for multiple apps to use, does. The XIP editor reserves the right to reject XIP proposals if they appear too unfocused or too broad. If in doubt, split your XIP into several well-focused ones.

Each XIP must have a champion - someone who writes the XIP using the style and format described below, shepherds the discussions in the appropriate forums, and attempts to build community consensus around the idea.

Vetting an idea publicly before going as far as writing an XIP is meant to save the potential author time. Asking the Expanse community first if an idea is original helps prevent too much time being spent on something that is guaranteed to be rejected based on prior discussions (searching the Internet does not always do the trick). It also helps to make sure the idea is applicable to the entire community and not just the author. Just because an idea sounds good to the author does not mean it will work for most people in most areas where Expanse is used. Examples of appropriate public forums to gauge interest around your XIP include [the Expanse subreddit], [the Issues section of this repository], and [one of the Expanse Gitter chat rooms]. In particular, [the Issues section of this repository] is an excellent place to discuss your proposal with the community and start creating more formalized language around your XIP.

Once the champion has asked the Expanse community whether an idea has any chance of acceptance a draft XIP should be presented as a [pull request]. This gives the author a chance to continuously edit the draft XIP for proper formatting and quality. This also allows for further public comment and the author of the XIP to address concerns about the proposal.

If the XIP collaborators approve, the XIP editor will assign the XIP a number (generally the issue or PR number related to the XIP), label it as Standards Track, Informational, or Meta, give it status “Draft”, and add it to the git repository. The XIP editor will not unreasonably deny an XIP. Reasons for denying XIP status include duplication of effort, being technically unsound, not providing proper motivation or addressing backwards compatibility, or not in keeping with the Expanse philosophy.

Standards Track EXPIPs consist of three parts, a design document, implementation, and finally if warranted an update to the [formal specification]. The XIP should be reviewed and accepted before an implementation is begun, unless an implementation will aid people in studying the XIP. Standards Track EXPIPs must be implemented in at least three viable Expanse clients before it can be considered Final.

For an XIP to be accepted it must meet certain minimum criteria. It must be a clear and complete description of the proposed enhancement. The enhancement must represent a net improvement. The proposed implementation, if applicable, must be solid and must not complicate the protocol unduly.

Once an XIP has been accepted, the implementations must be completed. When the implementation is complete and accepted by the community, the status will be changed to “Final”.

An XIP can also be assigned status “Deferred”. The XIP author or editor can assign the XIP this status when no progress is being made on the XIP. Once an XIP is deferred, the XIP editor can re-assign it to draft status.

An XIP can also be “Rejected”. Perhaps after all is said and done it was not a good idea. It is still important to have a record of this fact.

EXPIPs can also be superseded by a different XIP, rendering the original obsolete.

The possible paths of the status of EXPIPs are as follows:

<img src=./XIP-1/process.png>

Some Informational and Process EXPIPs may also have a status of “Active” if they are never meant to be completed. E.g. XIP 1 (this XIP).

What belongs in a successful XIP?
---------------------------------

Each XIP should have the following parts:

-   Preamble - RFC 822 style headers containing metadata about the XIP, including the XIP number, a short descriptive title (limited to a maximum of 44 characters), the names, and optionally the contact info for each author, etc.

<!-- -->

-   Simple Summary - “If you can’t explain it simply, you don’t understand it well enough.” Provide a simplified and layman-accessible explanation of the XIP.

<!-- -->

-   Abstract - a short (~200 word) description of the technical issue being addressed.

<!-- -->

-   Motivation (*optional) - The motivation is critical for EXPIPs that want to change the Expanse protocol. It should clearly explain why the existing protocol specification is inadequate to address the problem that the XIP solves. XIP submissions without sufficient motivation may be rejected outright.

<!-- -->

-   Specification - The technical specification should describe the syntax and semantics of any new feature. The specification should be detailed enough to allow competing, interoperable implementations for any of the current Expanse platforms (cpp-Expanse, go-Expanse, parity, ExpanseJ, Expansejs-lib, …).

<!-- -->

-   Rationale - The rationale fleshes out the specification by describing what motivated the design and why particular design decisions were made. It should describe alternate designs that were considered and related work, e.g. how the feature is supported in other languages. The rationale may also provide evidence of consensus within the community, and should discuss important objections or concerns raised during discussion.

<!-- -->

-   Backwards Compatibility - All EXPIPs that introduce backwards incompatibilities must include a section describing these incompatibilities and their severity. The XIP must explain how the author proposes to deal with these incompatibilities. XIP submissions without a sufficient backwards compatibility treatise may be rejected outright.

<!-- -->

-   Test Cases - Test cases for an implementation are mandatory for EXPIPs that are affecting consensus changes. Other EXPIPs can choose to include links to test cases if applicable.

<!-- -->

-   Implementations - The implementations must be completed before any XIP is given status “Final”, but it need not be completed before the XIP is accepted. While there is merit to the approach of reaching consensus on the specification and rationale before writing code, the principle of “rough consensus and running code” is still useful when it comes to resolving many discussions of API details.

XIP Formats and Templates
-------------------------

EXPIPs should be written in [markdown] format. Image files should be included in a subdirectory for that XIP.

XIP Header Preamble
-------------------

Each XIP must begin with an RFC 822 style header preamble. The headers must appear in the following order. Headers marked with "*" are optional and are described below. All other headers are required.

` XIP: ` <XIP number> (this is determined by the XIP editor)

` Title: `<XIP title>

` Author: `<list of author's real names and optionally, email address>

` * Discussions-To: ` <email address>

` Status: `<Draft | Active | Accepted | Deferred | Rejected | Withdrawn | Final | Superseded>

` Type: `<Standards Track (Core, Networking, Interface, ERC)  | Informational | Process>

` Created: `<date created on, in ISO 8601 (yyyy-mm-dd) format>

` * Replaces: `<XIP number>

` * Superseded-By: `<XIP number>

` * Resolution: `<url>

The Author header lists the names, and optionally the email addresses of all the authors/owners of the XIP. The format of the Author header value must be

Random J. User &lt;address@dom.ain&gt;

if the email address is included, and

Random J. User

if the email address is not given.

Note: The Resolution header is required for Standards Track EXPIPs only. It contains a URL that should point to an email message or other web resource where the pronouncement about the XIP is made.

While an XIP is in private discussions (usually during the initial Draft phase), a Discussions-To header will indicate the mailing list or URL where the XIP is being discussed. No Discussions-To header is necessary if the XIP is being discussed privately with the author.

The Type header specifies the type of XIP: Standards Track, Meta, or Informational. If the track is Standards please include the subcategory (core, networking, interface, or ERC).

The Created header records the date that the XIP was assigned a number. Both headers should be in yyyy-mm-dd format, e.g. 2001-08-14.

EXPIPs may have a Requires header, indicating the XIP numbers that this XIP depends on.

EXPIPs may also have a Superseded-By header indicating that an XIP has been rendered obsolete by a later document; the value is the number of the XIP that replaces the current document. The newer XIP must have a Replaces header containing the number of the XIP that it rendered obsolete.

Auxiliary Files
---------------

EXPIPs may include auxiliary files such as diagrams. Such files must be named XIP-XXXX-Y.ext, where “XXXX” is the XIP number, “Y” is a serial number (starting at 1), and “ext” is replaced by the actual file extension (e.g. “png”).

Transferring XIP Ownership
--------------------------

It occasionally becomes necessary to transfer ownership of EXPIPs to a new champion. In general, we'd like to retain the original author as a co-author of the transferred XIP, but that's really up to the original author. A good reason to transfer ownership is because the original author no longer has the time or interest in updating it or following through with the XIP process, or has fallen off the face of the 'net (i.e. is unreachable or not responding to email). A bad reason to transfer ownership is because you don't agree with the direction of the XIP. We try to build consensus around an XIP, but if that's not possible, you can always submit a competing XIP.

If you are interested in assuming ownership of an XIP, send a message asking to take over, addressed to both the original author and the XIP editor. If the original author doesn't respond to email in a timely manner, the XIP editor will make a unilateral decision (it's not like such decisions can't be reversed :).

XIP Editors
-----------

The current XIP editors are

` * Casey Detrio (@cdetrio)`

` * Fabian Vogelsteller (@frozeman)`

` * Gavin Wood (@gavofyork)`

` * Hudson Jameson (@Souptacular)`

` * Jeffrey Wilcke (@obscuren)`

` * Martin Becze (@wanderer)`

` * Nick Johnson (@arachnid)`

` * Roman Mandeleil (@romanman)`

` * Vitalik Buterin (@vbuterin)`

XIP Editor Responsibilities and Workflow
--------------------------------------

For each new XIP that comes in, an editor does the following:

-   Read the XIP to check if it is ready: sound and complete. The ideas must make technical sense, even if they don't seem likely to be accepted.
-   The title should accurately describe the content.
-   Edit the XIP for language (spelling, grammar, sentence structure, etc.), markup (Github flavored Markdown), code style

If the XIP isn't ready, the editor will send it back to the author for revision, with specific instructions.

Once the XIP is ready for the repository, the XIP editor will:

-   Assign an XIP number (generally the PR number or, if preferred by the author, the Issue # if there was discussion in the Issues section of this repository about this XIP)

<!-- -->

-   Accept the corresponding pull request

<!-- -->

-   List the XIP in [README.md]

<!-- -->

-   Send a message back to the XIP author with next step.

Many EXPIPs are written and maintained by developers with write access to the Expanse codebase. The XIP editors monitor XIP changes, and correct any structure, grammar, spelling, or markup mistakes we see.

The editors don't pass judgment on EXPIPs. We merely do the administrative & editorial part.

History
-------

This document is forked from [Ethereum's EIP-0001] which was derived heavily from [Bitcoin's BIP-0001] written by Amir Taaki which in turn was derived from [Python's PEP-0001]. In many places text was simply copied and modified. Although the PEP-0001 text was written by Barry Warsaw, Jeremy Hylton, and David Goodger, they are not responsible for its use in the Expanse Improvement Process, and should not be bothered with technical questions specific to Expanse or the XIP. Please direct all comments to the XIP editors.

June 11, 2017: XIP 1 has been improved and will be placed as a PR.

  [the Expanse subreddit]: https://www.reddit.com/r/ExpanseTech/
  [one of the Expanse Gitter chat rooms]: https://gitter.im/Expanse/
  [pull request]: https://github.com/Expanse/EXPIPs/pulls
  [the Issues section of this repository]: https://github.com/Expanse/EXPIPs/issues
  [markdown]: https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet
  [README.md]: README.md "wikilink"
  [Bitcoin's BIP-0001]: https://github.com/bitcoin/bips
  [Python's PEP-0001]: https://www.python.org/dev/peps/
