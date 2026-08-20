# GitHub Actions sweep

For each n in 2, 4, 8, 16:
1. Open n independent PRs (assigned modules only).
2. Stagger: start the second half after the first half is in CI, not merged.
3. Merge only when checks are green.
4. Record in telemetry.jsonl: n, task_id, t_start, t_ready, t_ci_green, t_landed, stale_on_main, rebase_needed, conversation_link.

land_rate = landed_green / wall_hours
stale_on_main = CI was green on an old main SHA, then red/recheck after another land.
