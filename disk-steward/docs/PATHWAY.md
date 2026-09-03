# Pathway

One owner per step. Do not skip ahead to Apply.

```
[0 Access check] → [1 Freeze roots] → [2 Inventory]
        → [3 Classify] → [4 Dry-run manifest] → [5 Human OK]
        → [6 Apply] → [7 Verify] → STOP
```

Abort if step 0 cannot see a root, step 1 has empty USER_ROOTS, or step 5 is missing for any destructive row.

## Step 0 — Access check

**Owner:** agent  
**Input:** environment  
**Output:** `OS`, hostname if available, which candidate roots exist  
**Do:** detect macOS / Linux / Windows; `stat` or equivalent each path in the index with status `proposed` or `active`.  
**Do not:** move files.  
**Stop / abort:** if zero roots exist, print the index and wait.

## Step 1 — Freeze roots

**Owner:** user (agent only proposes)  
**Input:** `docs/ROOTS_INDEX.md`  
**Output:** each working root set to `active` with a real path (no `YOU` placeholder)  
**Do not:** invent a username.

## Step 2 — Inventory

**Owner:** agent  
**Input:** active roots only  
**Output:** per-root counts by extension, top sizes, empty dirs, obvious duplicate-name pairs  
**Do not:** read secret file contents; if a path matches the secret patterns in the index, record `path + kind` only.

## Step 3 — Classify (plan)

**Owner:** agent  
**Input:** inventory  
**Output:** proposed dest tree *inside the same root* unless the index maps that root to an archive root  
**Rule:** if two dests fit, leave the file and list it under conflicts.

## Step 4 — Dry-run manifest

**Owner:** agent  
**Output columns:** `id | source | dest | action | risk | root_id`  
**Actions allowed in a dry-run:** `mkdir` (noted only), `move`, `copy`, `trash`, `quarantine`, `skip`.  
**No apply.**

## Step 5 — Human OK

**Owner:** user  
**Pass:** user pastes APPLY MANIFEST and/or marks row ids OK.  
**If silent:** do not apply. Stay at the manifest.

## Step 6 — Apply

**Owner:** agent  
**Input:** approved row ids only  
**Default remove:** Trash or `<root>/Quarantine`  
**Permanent unlink:** only if the user wrote `permanent` on that row.  
**On error:** stop that row, keep going on others, record failure.

## Step 7 — Verify

**Owner:** agent  
**Checks:** dest exists for each applied move; spot-check 3 paths; quarantine/trash count; list failed ids.  
**Then STOP.** No bonus refactors.

## Verbosity

- Default: short why + undo at steps 4 and 6.  
- User chip QUIET MODE: five blocks only (see `chips/quiet-mode.md`).  
- Failures and skips still print in quiet mode.
