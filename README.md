# truthcrawl

truthcrawl is an early-stage, open source tamper-evident transparency log for web crawl observations. Built with cryptographic signing, Merkle trees, and append-only logs to verify what was on a page and when.

## What this project is

- A standard observation schema for crawlers/verifiers
- A transparency log format (append-only) for publishing crawl receipts
- Reference implementations for:
  - observer nodes (fetch individual URLs and produce signed observations)
  - log publisher (build Merkle roots)
  - proof verifier (verify inclusion proofs)
- Analytics primitives for detecting manipulation patterns (optional layer)

## What this project is not

- A full web crawler (it fetches specific URLs you provide, it does not spider sites)
- A search engine or ranking system
- A store of full page content on-chain

## Roadmap

### Complete

- **M0: Spec Lock** -- Observation schema, transparency log format, Merkle tree spec, cryptographic decisions (SHA-256, Ed25519, deterministic serialization)
- **M1: Transparency Log MVP** -- Merkle tree construction/proof verification, batch manifests, signed batch publishing, batch verification
- **M2: Verification Sampling MVP** -- Observation records with node signing, record comparison, deterministic sampling for re-verification
- **M3: Dispute System** -- Dispute records, multi-node observation sets, majority consensus resolution, node reputation tracking
- **M4: Audit Pipeline & Batch Chain** -- Batch chaining with back-references, chain integrity verification, verification sampling, audit reports
- **M5: Record Store & Query** -- Hash-addressed file storage, URL and node indexing, chain-wide statistics
- **M6: Cross-Node Verification Pipeline** -- Batch export/import for offline exchange, automated verification pipeline, verification status tracking
- **M7: Trusted Timestamping** -- Ed25519 timestamp authority, timestamp tokens for records and batches, anti-backdating guarantees
- **M8: Content Archival** -- WARC-based page archival alongside content hashes, content retrieval by hash, storage lifecycle policies
- **M9: Network Layer** -- HTTP API for batch discovery and record exchange, peer registration, authenticated endpoints, autonomous node mode, peer sync
- **M10: Node Identity & Attestation** -- Operator identity binding, node registration protocol, attestation of crawl capabilities

### Planned

- **M11: Content Comparison** -- Structural similarity analysis between archived pages, diff generation, plagiarism-relevant field extraction
- **M12: Evidence Packaging** -- Court-ready evidence bundles with chain of custody, human-readable reports with cryptographic backing, third-party audit hooks

## Getting Started

See [USAGE.md](USAGE.md) for installation, Docker setup, CLI commands, and
multi-node configuration.

## Contributing

See CONTRIBUTING.md and docs/adr for architecture decisions.
