- Feature Name: `crate-overlays`
- Start Date: 2026-10-30

## Summary

[summary]: #summary

Allow organizations to publish an "overlay" for crates.io, which adds aditional crates and crate
versions that are not available on the main crates.io registry. This enables:

- A straightforward distribution mechanism for embargoed releases
- A unified view of an organization's internal crates and the ecosystem registry
- Allowing organizations to sell access to their overlays, to help fund maintenance

## Motivation

[motivation]: #motivation

Organizations often have internal crates that are not intended for public release. Today, they
must setup a private registry or other distribution mechanism to share these crates internally.
While this approach works and is currently being used, it comes with a number of drawbacks.

- A public crate (version) could inadvertently "shadow" an internal crate (version).
- It is too easy to accidentally publish to the public registry instead of the internal one.
- Managing multiple registries and their interactions is complex and error-prone.
- There is no easy way to share some internal crates (or versions) across organizations.
- Running your own registry requires significant operational overhead and maintenance effort.

## Guide-level explanation

[guide-level-explanation]: #guide-level-explanation

crates.io will allow organizations to publish overlays, which are collections of crates and
crate versions with a defined policy for visibility and access. Organizations can share their
overlays with other organizations, and consuming organizations can define a hierarchy of
overlays to determine how overlays are allowed to interact.

## Reference-level explanation

[reference-level-explanation]: #reference-level-explanation

TBD.

## Drawbacks

[drawbacks]: #drawbacks

It's hard.

## Rationale and alternatives

[rationale-and-alternatives]: #rationale-and-alternatives


## Prior art

[prior-art]: #prior-art


## Unresolved questions

[unresolved-questions]: #unresolved-questions

- What parts of the design do you expect to resolve through the RFC process before this gets merged?
- What parts of the design do you expect to resolve through the implementation of this feature before stabilization?
- What related issues do you consider out of scope for this RFC that could be addressed in the future independently of the solution that comes out of this RFC?

## Future possibilities

[future-possibilities]: #future-possibilities
