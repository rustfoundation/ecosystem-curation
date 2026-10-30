- Feature Name: `custom-crates-index-views`
- Start Date: 2026-10-30

## Summary

[summary]: #summary

Allow organizations to configure a custom view of the crates.io registry contents.
This would allow organizations to customize the view of available crate versions:

- Restrict access to specific crates
- Restrict access to certain crate versions
- Enforce cooldown policies in a central location
- Require published cargo-vet reviews

## Motivation

[motivation]: #motivation

Most Rust projects make heavy use of the rich ecosystem of open source crates available on
crates.io. While the Rust language itself provides many benefits, the ecosystem of supporting
packages is essential to an effective development experience for Rust applications.

At the same time, using third-party dependencies means trusting maintainers with which an
organization likely has no direct relationship, and the size of common dependency graphs
can mean that even disciplined applications are trusting many maintainers indirectly.

Custom views of the crates.io registry can help organizations manage this trust by allowing them
to enforce policies and restrictions centrally, rather than relying on the discretion of
application contributors or decentralized tooling (like `cargo update`).

## Guide-level explanation

[guide-level-explanation]: #guide-level-explanation

crates.io will implement support for custom views of the registry. Organizations can sign up
for a custom view, which will be private to the organization. API calls that list crates
and crate versions are filtered according to the organization's configured policies.

Organizations can configure which crates and crate versions are visible in their custom view,
as well as enforce policies such as cooldown periods and required cargo-vet reviews. This
allows organizations to centrally manage their dependency policies and ensure compliance across
all projects using the custom view.

## Reference-level explanation

[reference-level-explanation]: #reference-level-explanation

TBD.

## Drawbacks

[drawbacks]: #drawbacks

It's hard.

## Rationale and alternatives

[rationale-and-alternatives]: #rationale-and-alternatives

If we don't implement something like this, some organizations will likely go and create their own
private registry implementations. This seems to already be happening to some extent, resulting in
wasted effort and fragmentation from multiple organizations maintaining their own private
registries with overlapping functionality and inconsistent policies.

Alternatively, a third-party service could provide similar functionality. It would likely be
harder to achieve widespread adoption compared to an official solution integrated with crates.io,
and makes it harder for the crates.io interface to interoperate with the third-party service.

## Prior art

[prior-art]: #prior-art

[Haven](https://haven.rs/docs/) is an implementation of some of the ideas in this RFC, providing
organizations with their own registry that can enforce custom policies.

## Unresolved questions

[unresolved-questions]: #unresolved-questions

- What parts of the design do you expect to resolve through the RFC process before this gets merged?
- What parts of the design do you expect to resolve through the implementation of this feature before stabilization?
- What related issues do you consider out of scope for this RFC that could be addressed in the future independently of the solution that comes out of this RFC?

## Future possibilities

[future-possibilities]: #future-possibilities

Some policies could be made available only to customers paying for premium access, providing one
avenue to generate revenue for the Foundation from crates.io usage.
