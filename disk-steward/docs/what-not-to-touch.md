# What not to touch

Cite an `X-*` id from ROOTS_INDEX when refusing.

- Operating system trees and package managers’ system prefixes.
- Other users’ home directories.
- `~/Library` on macOS (this is not Downloads clutter).
- SSH, GnuPG, cloud CLI credential dirs.
- Secret-looking files: record path and kind; do not cat them into chat.
- Mass delete of “unused” files with no age/type/path rule.
- Format, wipe, disable security tools, offensive scanning of third-party systems.

If the user names one exact file under an exclude and a reason, ask once, then act only on that file.
