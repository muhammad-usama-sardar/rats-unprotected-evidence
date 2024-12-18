---
###
# Internet-Draft Markdown Template
#
# Rename this file from draft-todo-yourname-protocol.md to get started.
# Draft name format is "draft-<yourname>-<workgroup>-<name>.md".
#
# For initial setup, you only need to edit the first block of fields.
# Only "title" needs to be changed; delete "abbrev" if your title is short.
# Any other content can be edited, but be careful not to introduce errors.
# Some fields will be set automatically during setup if they are unchanged.
#
# Don't include "-00" or "-latest" in the filename.
# Labels in the form draft-<yourname>-<workgroup>-<name>-latest are used by
# the tools to refer to the current version; see "docname" for example.
#
# This template uses kramdown-rfc: https://github.com/cabo/kramdown-rfc
# You can replace the entire file if you prefer a different format.
# Change the file extension to match the format (.xml for XML, etc...)
#
###
title: "Using Conveyance Protocol for Unprotected Evidence in RATS Architecture"
abbrev: "unprotected-evidence"
category: info

docname: draft-usama-rats-unprotected-evidence-latest
updates: 9334
submissiontype: IETF  # also: "independent", "editorial", "IAB", or "IRTF"
number:
date:
consensus: true
v: 3
area: Security
workgroup: RATS Working Group
keyword:
 - attestation
 - RATS
venue:
  group: RATS
  type: Working Group
  mail: rats@ietf.org
  github: muhammad-usama-sardar/rats-unprotected-evidence
  latest: https://example.com/LATEST

author:
 -
    fullname: Muhammad Usama Sardar
    organization: TU Dresden
    email: muhammad_usama.sardar@tu-dresden.de

normative:
  RFC9334: rfc9334
  
informative:
  RFC8446: rfc8446

--- abstract

This document provides corrections to RFC9334. 


--- middle

# Introduction

RFC9334 presents the RATS architecture. 
However, some parts of the specification contain errors that may lead to misinterpretations and even insecure implementations. 
This document provides corrections to RFC9334. 


# Conventions and Definitions

{::boilerplate bcp14-tagged}

# Corrections
{{Section 7.4 of -rfc9334}} has:

{:quote}
>  A conveyance protocol that provides authentication and integrity protection can be used to convey Evidence that is otherwise unprotected (e.g., not signed).

Using a conveyance protocol that provides authentication and integrity protection, such as TLS 1.3 {{-rfc8446}}, to convey Evidence that is otherwise unprotected (e.g., not signed) undermines all security of remote attestation. Essentially, this breaks up the chain up to the root of trust. Effectively, remote attestation provides no protection in this case and the security guarantees are limited to those of the conveyance protocol only. In order to benefit from remote attestation, it is recommended that Evidence MUST be protected using dedicated keys chaining back to the root of trust.

# Security Considerations

All of this document is about security considerations.


# IANA Considerations

This document has no IANA actions.


--- back

# Acknowledgments
{:numbered="false"}

TODO acknowledge.
