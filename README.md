# Registrant

Registrant publishes optional descriptions for BSV wallet protocols, output
baskets and certificate types through ProtoMap, BasketMap and CertMap.
Descriptions are signed statements from individual registry publishers. They
help users understand a request; they do not grant wallet permissions, approve
an application or give the publisher control over use of a protocol.

## Builders: request a useful description

Start with the [BRC process](https://github.com/bsv-blockchain/BRCs#contributing):
document the exact identifiers and semantics in a proposal or improve an existing
BRC. Request inclusion in a linked BRC issue, discussion or proposal conversation,
and tag the relevant maintainer. For **Metanet Trust Services**, tag **@ty-everett**.
For **genuinely urgent or long-time unresolved matters**, email the BRC author at
[ty@projectbabbage.com](mailto:ty@projectbabbage.com). The normal route is the
[BRC issues](https://github.com/bsv-blockchain/BRCs/issues/new/choose) or
[discussions](https://github.com/bsv-blockchain/BRCs/discussions).

Provide the publisher/network, exact protocol tuple, basket or certificate type,
plain description, public documentation, usable icon, implementation evidence
and any certificate-field descriptors. This early editorial process will improve
with use; it is not a prerequisite to building or using a protocol. A BRC merge
does not automatically publish a registry record.

## Publishers: manage your own signed records

The UI connects a signing wallet, lists its own records, and offers create,
update and remove operations using the SDK's `RegistryClient`. Publishing with
your own wallet does not publish as another operator or add your key to another
wallet's defaults. Authors seeking an existing operator's listing should request
review, not request the operator's key.

See [registry operation and authority boundaries](./docs/registry-operations.md)
for identity, resource quality, updates, withdrawals, verification and recovery.
The current source offers wallet login and private-key login; the latter retains
the key in browser session storage. Use an appropriately secured operator wallet
and custody process. This documentation is not a claim that a public deployment
is running this exact source revision.

## Optional metadata and stewardship

The proposed [BRC-184: Optional Metadata Registries and Their Stewardship](https://github.com/bsv-blockchain/BRCs/pull/271)
explains the intended boundary: impartial public information, a lightweight
BRC-based inclusion and dispute process, and replaceable registry publishers.
The IANA service/port registry is an analogy for coordination, not an affiliation
or a grant of authority to allocate exclusive protocol rights.

Wallets adopting that profile must keep a usable normal permission flow when
metadata is missing, disputed, withdrawn or unavailable. A listing cannot grant
permissions, and omission cannot impose a protocol block or extra approval
barrier. Users can still deny requests, and wallets enforce their ordinary
validation, spending and supported-module rules independently.

Different wallets and communities may choose other publishers. Public on-chain
records can be independently verified and replicated where available, preserving
attribution. Linked images and documentation need separate preservation. The
proposal does not claim all current wallets are already conformant or that a
formal independent dispute tribunal exists.

## License

The code in this repository uses the Open BSV License. See [LICENSE.txt](./LICENSE.txt).
