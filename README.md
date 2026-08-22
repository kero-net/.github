# kero-net GitHub Control Plane

This special repository provides the organization profile and default community
health files for repositories in [`kero-net`](https://github.com/kero-net).

Repository-specific implementation, release automation, and documentation
belong to their owning repositories:

- [`src`](https://github.com/kero-net/src) is KERO's canonical source.
- [`kero`](https://github.com/kero-net/kero) is KERO's public release,
  discussion, issue, and package surface.

GitHub uses eligible files in this public repository only when an individual
repository has no local override. Do not put source-repository CI or release
workflows here merely to make them shared; callers must explicitly invoke
reusable workflows.
