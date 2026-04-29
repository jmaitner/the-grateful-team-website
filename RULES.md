# Workflow Rules — The Grateful Team Website

These rules are mandatory and must never be deviated from.

## Repository

- GitHub repo: https://github.com/jmaitner/the-grateful-team-website
- Working branch: `luis`
- Source of truth: `main` (managed by Jackson)

---

## Session Model

Work happens in **sessions**. A session is a continuous block of work — one sitting, one topic, one day's changes. You do NOT pull from main before every single change. You pull once at the start of a new session, work as long as you need, and end the session cleanly when you're done.

---

## START SESSION Checklist

Before touching any file, run through this checklist:

**1. Has Jackson merged `luis` into `main` since your last session?**
- Ask Jackson, or check on GitHub, whether your previous changes made it into `main`.
- If yes → pull from main (step 2).
- If no and you're continuing your own unmerged work → you may skip the pull and continue on `luis` where you left off. Confirm with Claude before skipping.

**2. Pull the latest `main`**
```bash
git checkout main
git pull origin main
```

**3. Switch to `luis` and sync it with main**
```bash
git checkout luis
git merge main
```

**4. You're ready — make your changes on `luis`.**

---

## DURING A SESSION

- Stay on the `luis` branch the entire time.
- Push to `luis` as often as you like — after each change, after a group of changes, whenever you want a save point:
  ```bash
  git push origin luis
  ```
- **Do not pull from main again mid-session.** You already have the latest. Pulling mid-session risks conflicts and confusion.
- **Never push to `main` directly.**
- **Never create new branches.**

---

## END SESSION Checklist

When you're done for the day (or done with a block of work), run through this before closing:

**1. Push your final changes to `luis`**
```bash
git push origin luis
```

**2. Confirm with Claude that everything is pushed.**
Claude will verify the branch is up to date before you stop.

**3. Tell Jackson** that `luis` is ready to review and merge into `main` if the changes are complete.

**4. Session is closed.** You cannot start the next session until:
- Jackson has confirmed whether he has merged `luis` into `main`, and
- You have pulled from `main` at the start of the new session (step 1 of START SESSION).

---

## Branch Rules

- **Two branches only:** `main` (Jackson's, do not touch) and `luis` (Luis's working branch).
- **Never create new branches.**
- **Never push to `main`.**
- **Always push to `luis`.**
- `luis` was created from `main` and should stay in sync with it at the start of each session.
