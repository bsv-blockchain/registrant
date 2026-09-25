# Registry operation and authority boundaries

Registrant is a publication tool, not the registration authority for all BSV
protocols. The wallet that signs a record identifies its publisher. Metanet Trust
Services is one such publisher, not a fourth record type or a BRC-100 requirement.

## Identify the record exactly

| Type | Lookup identity | Publisher wallet basket | Overlay topic / lookup |
| --- | --- | --- | --- |
| Protocol | `[securityLevel, protocolString]` | `protomap` | `tm_protomap` / `ls_protomap` |
| Basket | Basket identifier | `basketmap` | `tm_basketmap` / `ls_basketmap` |
| Certificate | Type bytes as base64 | `certmap` | `tm_certmap` / `ls_certmap` |

Include the network and publisher public key when identifying a record. A display
name or BRC number is insufficient. A certificate type differs from its issuer;
a type description does not endorse every issuer using it. Certificate field
names are case-sensitive and must match signed data. A basket description does
not authorize spending its outputs.

The current SDK uses one-satoshi signed PushDrop outputs, with the respective
`[1, registryName]` signing protocol, key ID `1` and `anyone` counterparty. Hosting
or indexing those records does not grant their publishing key.

## Before publishing

Review the BRC proposal and exact implementation identifiers with the author.
Record the intended publisher and network, evidence revisions, metadata changes
and reasons in the public BRC conversation. Metanet Trust Services requests and
disputes use BRC issues/discussions or the linked proposal, tagging @ty-everett;
urgent or long-unresolved escalation goes to ty@projectbabbage.com. Do not put
private operator material in the public conversation.

Prefer a short, accurate name and plain explanation of the capability or data.
Keep marketing, approval claims and pending editorial instructions out of the
published description. Include public, maintainable documentation and a working
image with appropriate reuse rights. A signature authenticates your statement;
it does not make an incorrect description true. Verify certificate field spelling,
meaning and display type against actual issuance, preserving legacy fields where
needed to understand existing certificates.

Confirm your wallet's public identity, network, recoverable key custody and wallet
records, and fee funds. Use the exact current spendable record for an update or
withdrawal. A publisher identity alone is not a backup of wallet state. Do not
share publication keys with requesters or put keys in issues, screenshots or logs.
The current private-key login path stores a root key in browser session storage;
that is a custody choice requiring an appropriate operator environment, not a
requirement for builders requesting descriptions.

## Lifecycle and verification

| UI operation / SDK method | On-chain effect | Editorial meaning |
| --- | --- | --- |
| Create / `registerDefinition` | Creates a signed record output | Publish this identity's description |
| Update / `updateDefinition` | Spends the old output and creates a replacement | Correct metadata while preserving the exact identifier |
| Remove / `removeDefinition` | Spends the record without a replacement | Withdraw this publisher's current description |

No operation bans a protocol, revokes user permissions or certificates, transfers
application assets, or erases blockchain history. Deleting a database row is not
a signed withdrawal. An old indexed row is not proof of a current spendable token.

After publication, verify the expected new outpoint and fields through public
lookup, confirm the old output is no longer current for an update/removal, and
check wallet presentation. Preserve the source revision, review decision,
transaction identifiers and validation evidence. A UI success message or a single
host's result does not establish every host's freshness. If broadcasting has an
uncertain outcome, reconcile the wallet, chain and overlay observations before
retrying; a duplicate create or a second spend attempt is not recovery.

A correction to an erroneous update is another signed update. Recovering from a
withdrawal requires a new record; neither restores the original outpoint. Keep
old metadata and reasons so the history is understandable.

## Stewardship and exit

Apply impartial, published editorial criteria across competing builders. Record
reasons for deferral, correction and withdrawal; disclose conflicts and seek
uninvolved review where practicable; accept evidence and reconsideration. Follow
the dispute process adopted as the community grows, while stating present limits.
There is no promise here of a formal tribunal or fixed response SLA. Listing does
not grant exclusive rights to an identifier, and a technical dispute should not
be disguised as an assertion of universal authority.

Registry content is optional. A wallet adopting the proposed BRC-184 profile
continues the normal permission flow with exact identifiers when metadata is
missing or unusable; it cannot turn a steward's editorial action into a protocol
veto. Conversely, a record cannot auto-approve a request. Supported-module rules,
validation and the user's decisions remain separate.

Independent hosts may serve authentic available records while preserving their
publisher attribution. Another publisher may issue its own descriptions under a
new identity, and communities or wallets may choose those sources. Replication
needs transaction data and correct current-state reconstruction; linked icons
and documentation are external resources. It does not convey the original key or
authority to edit another publisher's outputs. Document these continuity limits
instead of implying that a public chain makes all services permanently available.

See the [BRC process](https://github.com/bsv-blockchain/BRCs#contributing) for
protocol documentation and public discussion, and
[TS Stack](https://github.com/bsv-blockchain/ts-stack) for the SDK and overlay
implementations. Refer to the [BRC-184 proposal](https://github.com/bsv-blockchain/BRCs/pull/271) for the full proposed framework;
this documentation does not certify every current wallet implementation.
