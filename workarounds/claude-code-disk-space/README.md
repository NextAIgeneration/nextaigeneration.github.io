# Claude Code Disk Space Workaround

**Problem:** `~/.claude` grows unbounded — no rotation, no cleanup, no warnings.
**Impact:** 3.2 GB+ on a 500 GB internal SSD after ~2 months of daily usage.
**Related issues:** [#24207](https://github.com/anthropics/claude-code/issues/24207) · [#10107](https://github.com/anthropics/claude-code/issues/10107) · [#18869](https://github.com/anthropics/claude-code/issues/18869)

---

## The Problem

Claude Code stores conversation transcripts, file history, and debug data in `~/.claude/projects` with:

- **No rotation policy** — old sessions never cleaned up
- **No size monitoring** — no warnings before disk fills
- **No user-configurable storage path** — hardcoded to `~/.claude`
- **No `claude --cleanup`** — no manual garbage collection

Users have reported **200 GB to 472 GB** consumed silently.

## Solution: Symlink to External Storage

Redirect `~/.claude/projects` to an external SSD via symlink. Claude Code follows symlinks transparently.

### Steps

```bash
# 1. Check current disk usage
du -sh ~/.claude/projects

# 2. Copy existing data to external drive (preserve permissions)
cp -a ~/.claude/projects /Volumes/ExternalSSD/claude-data/projects

# 3. Verify copy integrity
diff -rq ~/.claude/projects /Volumes/ExternalSSD/claude-data/projects

# 4. Backup original
mv ~/.claude/projects ~/.claude/projects.backup

# 5. Create symlink
ln -s /Volumes/ExternalSSD/claude-data/projects ~/.claude/projects

# 6. Verify
ls -la ~/.claude/projects
claude --version  # confirm Claude Code still works
```

### Undo (if needed)

```bash
rm ~/.claude/projects
mv ~/.claude/projects.backup ~/.claude/projects
```

## Results

| Metric | Before | After |
|--------|--------|-------|
| Internal SSD used by Claude | 3.2 GB | 0 B (symlink) |
| Survives macOS restart | N/A | Yes (Sequoia 15.x) |
| Performance impact | N/A | None (USB-C SSD) |
| Claude Code compatibility | N/A | Fully transparent |

## What Anthropic Should Fix

1. **`CLAUDE_DATA_DIR` env var** — let users choose where data lives
2. **Automatic rotation** — prune sessions older than N days
3. **Size cap with warning** — alert at configurable threshold (e.g. 1 GB)
4. **`claude --cleanup`** — manual garbage collection command
5. **Disk usage display** — show `~/.claude` size in `claude --version` or settings

## Environment

- macOS Sequoia 15.x
- Mac Studio M1 Max, 500 GB internal SSD
- External SSD 2 TB (USB-C)
- Claude Code (latest)

## Contact

For questions or support: **vincent@fredfrenchtouch.io**

---

*[NextAIgeneration](https://github.com/NextAIgeneration) · FFT — Fred French Touch SRL*
