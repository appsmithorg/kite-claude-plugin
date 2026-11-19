---
name: kite
description: Use when the user asks about their Kite team, tasks, websites, research, videos, social posts, or approvals, or wants Kite to change or publish a website.
---

# Working with Kite

Kite is an AI marketing team. The `kite` connector reads and acts on one team at a time.

## Find the ids first

- Call `list_teams` to get the `team_id`. Every other tool needs it.
- Call `list_tasks` to get a `task_id`.
- Call `list_websites` to get a `website_id`.

If the user has more than one team or website, ask which one they mean.

## Confirm before anything that changes or costs

Tell the user what will happen and ask them to confirm before you call a tool that:

- changes a website: `request_website_change`, `merge_draft`, `publish_website`
- starts work that uses Kite credits: `start_research`, `create_research_website`, `build_website`, `create_video`
- answers an approval: `approve_alert_draft`, `skip_alert_draft`, `approve_social_post`, `decline_social_post`
- cancels a task: `cancel_task`

## Publish a website safely

1. Call `get_publish_preview` and show the user everything that publishing would ship.
2. After the user confirms, call `publish_website`. It makes exactly that list live.
3. Call `get_publish_status` and report how it went.

Use the same pattern for a draft. Show it with `get_draft`, then merge that exact revision with `merge_draft`.

## Follow started work

A tool that starts work returns a `task_id`. Follow it with `get_task_status`, then read the result with `get_task_result`. Follow a video with `get_video` instead.

## When Kite is waiting on the user

- `list_pending_approvals` shows what Kite needs the team to approve.
- If a video waits for a concept, ask the user to pick one, then call `choose_video_concept`.
- If the approval cannot be answered through a tool, give the user the item's `kite_url` so they can answer in Kite.

## Limits

- Research does not authorize outreach, schedules, or website edits. Each needs its own confirmed action.
- `cancel_task` does not undo past effects or stop subtasks.
