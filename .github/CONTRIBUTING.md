# Contributing

Development targets the `source` branch. Keep changes within an explicitly
documented layer or boundary and include tests derived from its contract.

Before opening a pull request, run:

```bash
cd src
cargo fmt --all --check
cargo clippy --all-targets --all-features -- -D warnings
cargo test --all-targets --locked
cargo build --release --locked
cd ..
python .github/scripts/validate-repository.py
python .github/scripts/test-localization.py
python .github/scripts/test-publication.py
python .github/scripts/test-publication-manifests.py
bash -n .github/scripts/*.sh
bash .github/scripts/run-actionlint.sh
```

Layer 2 must remain pure authorization. Layer 3 consumes authenticated Layer 2
artifacts and must not recompute or reinterpret policy. New `ENFORCED` claims
require a named operation, threat model, boundary, bypass analysis, and failure
tests. Never commit generated state, keys, credentials, audit logs, or local
absolute paths.
