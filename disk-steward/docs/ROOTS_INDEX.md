# USER_ROOTS index

Replace `YOU` and set **Status** to `active` before the agent inventories.

**OS:** `UNSET` — one of `macOS` | `Linux` | `Windows`  
**User placeholder:** `YOU`  
**Quarantine pattern:** `<root>/Quarantine`  
**Archive pattern:** only if a row’s *Maps to* column is filled

How to read a row:

- **ID** — use in manifests (`root_id`).
- **Role** — why this folder exists.
- **In** — agent may list / plan / move *inside* this path.
- **Out** — still under the path but do not touch.
- **Status** — `template` (has `YOU`) | `proposed` | `active` | `excluded`.

---

## A. Default in-scope roots (single-user laptop)

### macOS

| ID | Path | Role | In | Out | Status |
|---|---|---|---|---|---|
| R-DL | `/Users/YOU/Downloads` | Inbox. Sort or quarantine; do not keep as archive. | files and subfolders except Out | `Quarantine/` until Apply says so | template |
| R-DT | `/Users/YOU/Desktop` | Short-term visible files | same | Screenshots you asked to keep on Desktop | template |
| R-DOC | `/Users/YOU/Documents` | Long-lived user docs | same | `Documents/Library`-style app data if present | template |
| R-ARC | `/Users/YOU/Archive` | Optional dest for aged Downloads | create only after user OK | nothing else | template |

### Linux

| ID | Path | Role | In | Out | Status |
|---|---|---|---|---|---|
| R-DL | `/home/YOU/Downloads` | Inbox | same as macOS | `Quarantine/` | template |
| R-DT | `/home/YOU/Desktop` | Short-term | same | — | template |
| R-DOC | `/home/YOU/Documents` | Long-lived docs | same | — | template |
| R-ARC | `/home/YOU/Archive` | Optional aged dest | after OK | — | template |

### Windows

| ID | Path | Role | In | Out | Status |
|---|---|---|---|---|---|
| R-DL | `C:\Users\YOU\Downloads` | Inbox | same | `Quarantine\` | template |
| R-DT | `C:\Users\YOU\Desktop` | Short-term | same | — | template |
| R-DOC | `C:\Users\YOU\Documents` | Long-lived docs | same | — | template |
| R-ARC | `D:\Archive` | Optional dest if a data drive exists | after OK | other drive letters not listed | template |

---

## B. Common extras (off until you activate)

| ID | Typical path | Role | Status | Instruction |
|---|---|---|---|---|
| R-PIC | `~/Pictures` or `C:\Users\YOU\Pictures` | Photos | excluded | Activate only for rename/dedupe. Never bulk-delete. |
| R-MOV | `~/Movies` or `Videos` | Video | excluded | Same. |
| R-DEV | `~/dev`, `~/src`, `~/Projects` | Code | excluded | Not an “organize by type” target. No moving `node_modules` as a cleanup win without OK. |
| R-DOT | `~` home top-level | Dotfiles | excluded | Do not sweep `.*` into Archive. |
| R-USB | `/Volumes/*` or `E:\` | Removable | excluded | Activate for that session only. |

---

## C. Hard excludes (never USER_ROOTS)

Indexed so the agent can cite an ID when it refuses.

| ID | Path / pattern | Why |
|---|---|---|
| X-SYS-MAC | `/System`, `/usr`, `/bin`, `/sbin`, `/Library`, `/private` | OS |
| X-LIB-MAC | `/Users/YOU/Library` | App state; not clutter |
| X-SYS-LIN | `/bin`, `/sbin`, `/usr`, `/etc`, `/var`, `/boot`, `/root` | OS |
| X-SYS-WIN | `C:\Windows`, `C:\Program Files`, `C:\Program Files (x86)` | OS |
| X-WIN-SXS | `C:\Windows\WinSxS` | Component store |
| X-OTHER | `/Users/*` or `/home/*` or `C:\Users\*` other than YOU | Not yours |
| X-SSH | `~/.ssh` | Keys; report path exists only |
| X-GNUPG | `~/.gnupg` | Keys |
| X-AWS | `~/.aws`, `~/.config/gcloud` | Creds |
| X-ENV | any `**/.env`, `**/*.pem`, `**/id_rsa`, `**/*wallet*` | Secret-looking; path+kind only |
| X-CLOUD | unmounted Drive/Dropbox/OneDrive internals | Not local-owned until mounted *and* listed in section A |

Full prose: [what-not-to-touch.md](what-not-to-touch.md).

---

## D. Secret-looking patterns (flag, do not open)

`*.pem` `*.key` `id_rsa` `id_ed25519` `.env` `.env.*` `*credentials*` `*secret*` `*.kdbx` `*wallet*` `*.pfx` `*.p12`

Manifest action for these: `skip` or `quarantine` only if the user marked the row OK. Never print file contents.

---

## E. Freeze block (paste into a user message or the system prompt)

```text
OS: [macOS | Linux | Windows]
USER_ROOTS (active):
  R-DL  [full path]
  R-DT  [full path]
  R-DOC [full path]
USER_ROOTS (excluded this session):
  [IDs]
```

Until `OS` is set and at least one `R-*` path has no `YOU`, the agent stays at pathway step 0–1.
