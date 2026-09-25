# Registrant frontend

The React UI connects a publisher's wallet and creates, updates or withdraws
optional ProtoMap, BasketMap and CertMap descriptions through RegistryClient.

See the [project README](../README.md) for the builder submission process and
[operator guide](../docs/registry-operations.md) for record identity, custody,
publication verification and authority boundaries. Protocol documentation and
inclusion requests belong in the BRC process, not in a request for an operator key.

Registry metadata does not grant wallet permissions or control protocol access.
Missing or withdrawn descriptions must not become a protocol veto in wallets
adopting the proposed BRC-184 profile.

The code uses the [Open BSV License](../LICENSE.txt).
