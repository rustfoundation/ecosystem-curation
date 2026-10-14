- Feature Name: `ecosystem-support``
- Start Date: 2026-10-14`

## Summary

[summary]: #summary

Start an Ecosystem Support program within the Rust Foundation.

The Ecosystem Support program will:

1. Facilitate the crates.io ecosystem by encouraging organizations to contribute funding
   and other resources to support the continued development and maintenance of the Rust
   crates ecosystem.
2. Where necessary, assist organizations using Rust crates by helping to maintain crates
   whose maintainers are unable to provide timely maintenance and support for their users.
3. In doing so, avoid unnecessary centralization of resources/maintenance efforts, seeking
   to enable individual maintainers to sustainably maintain their own crates.

In order to avoid demotivating crate maintainers, these priorities are explicitly ordered
as above.

## Motivation

[motivation]: #motivation

Most Rust projects make heavy use of the rich ecosystem of open source crates available on
crates.io. While the Rust language itself provides many benefits, the ecosystem of supporting
packages is essential to an effective development experience for Rust applications.

While the Rust Project and its funding team have focused on Rust Project components (like
the compiler, the standard libraries, Cargo, rustup and other essential parts of the
experience), Project and Foundation have so far done relatively little to directly support
maintainers that are essential to the broader Rust ecosystem.

At the same time, increased usage of LLMs to find issues and security problems have meant
a substantial increase in the rate of (often security-sensitive) issues and pull requests
to review, adding additional strain on maintainers who are often uncompensated for the
highly leveraged value they provide to the broader Rust ecosystem.

## Guide-level explanation

[guide-level-explanation]: #guide-level-explanation

The Ecosystem Support program encourages organizations using Rust to contribute funding
(or other resources, like helping out with maintenance directly) to support the continued
development and maintenance of the Rust crates they rely on in their application. The
Foundation will seed the Ecosystem Support program with 5% of all incoming membership fees.

1. An organization uploads a collection of `Cargo.lock` files, allowing the program
   to specifically target funds towards the crates they depend on.
2. On a monthly basis, funding is provided to the maintainers of these crates, only
   for maintainers that have signed up for the program.
3. In return for this funding, tooling will notify participating organizations of changes
   in the status of open security advisories in the crates they depend on.
4. Maintainers can send surveys to participating organizations to gather feedback on the
   future development roadmap.
5. Maintainers will attest to the quality of their crates to assist organizations in
   complying with applicable regulations.

Both organizations and maintainers can sign up on a self-serve basis, allowing the
program to scale with minimal administrative overhead.

For crates whose maintainers are unable to maintain their crates in a timely fashion,
the Ecosystem Support program will add support for Overlays to crates.io. Overlays
allow provider organizations to publish additional versions of crates that may include
additional fixes (including security patches). Crate versions published via an overlay
must not prevent the original crate from publishing new versions, so overlay versions
should be pre-releases for an unpublished semver range or patch releases for an
existing version. crates.io will provide an index into overlays, allowing consuming
organizations to contact the overlay maintainers directly and purchase access.
Users that authenticate with crates.io as part of a consuming organization will then
be able to access the overlay versions according to the permissions granted to their
organization.

## Reference-level explanation

[reference-level-explanation]: #reference-level-explanation

TBD.

## Drawbacks

[drawbacks]: #drawbacks

It's hard.

## Rationale and alternatives

[rationale-and-alternatives]: #rationale-and-alternatives

The ecosystem naturally exists as a two-sided marketplace:

- Maintainers provide ongoing crate maintenance
- Organizations consume their crates and give feedback

Unfortunately, too often the organizations capturing substantial value from the maintainers' work
do not provide adequate compensation to the maintainers. This is especially true for crates
that might live lower on the stack but still address substantial complexity.

The Foundation is well-suited to playing a role in moderating the marketplace, clarifying
expectations for both maintainers and organizations. By improving scalability of the funding
process, the Foundation can ensure the existence of a high-quality, well-maintained ecosystem
of crates, supported by maintainers with a sustainable livelihood (and less burnout).

For those maintainers where funding provided by this program is insufficient to be able to
spend time on maintaining their crates, the Foundation will additionally facilitate
alternative providers of maintenance via crates.io overlays. This might prove especially
important in the current onslaught of LLM-assisted defect discovery.

However, if the program focused too much on the needs of large organizations consuming crates
(over the needs of the maintainers providing value via their crates), it could undermine both
sustained maintenance and future development of new, innovative libraries.

## Prior art

[prior-art]: #prior-art

thanks.dev provides a platform that allows organizations to fund package maintainers of
open source projects across many ecosystems. Anecdotal evidence has shown it has not led
to significant improvements in the long-term sustainability of maintainers.

GitHub Sponsors is a GitHub program to allow organizations and individuals to financially
support open source maintainers. While there are a small number of highly visible maintainers
drawing substantial income, the overwhelming majority of maintainers receive little support
through this program. A substantial part of the incoming funding appears to come from
individuals seeking to support maintainers whose work they appreciate, rather than the
organizations actually capturing the value of those projects.

The Rust Project's t-funding team has sought to find funding for Rust Project Goals, and
has found some success in doing so. So far, they have not sought to provide funding for
the crates ecosystem, and doing so could be harder because of the different scale.
Nonetheless, it feels like the cohesion of the Rust community could provide a more fertile
ground for funding models like this compared to the more generic platforms mentioned above.

## Unresolved questions

[unresolved-questions]: #unresolved-questions

- What parts of the design do you expect to resolve through the RFC process before this gets merged?
- What parts of the design do you expect to resolve through the implementation of this feature before stabilization?
- What related issues do you consider out of scope for this RFC that could be addressed in the future independently of the solution that comes out of this RFC?

## Future possibilities

[future-possibilities]: #future-possibilities

Think about what the natural extension and evolution of your proposal would
be and how it would affect the language and project as a whole in a holistic
way. Try to use this section as a tool to more fully consider all possible
interactions with the project and language in your proposal.
Also consider how this all fits into the roadmap for the project
and of the relevant sub-team.

This is also a good place to "dump ideas", if they are out of scope for the
RFC you are writing but otherwise related.

If you have tried and cannot think of any future possibilities,
you may simply state that you cannot think of anything.

Note that having something written down in the future-possibilities section
is not a reason to accept the current or a future RFC; such notes should be
in the section on motivation or rationale in this or subsequent RFCs.
The section merely provides additional information.
