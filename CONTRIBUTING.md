# Contributing to introducejobs

There are three ways listings end up on this board:

## 1. Manual submission (anyone, no GitHub skill needed)
Open a [Job Submission Issue](../../issues/new/choose). Fill in the form. A maintainer reviews and merges it into `jobs.yaml`.

## 2. Direct PR (comfortable with GitHub)
1. Fork the repo
2. Add your entry to `jobs.yaml` following the existing format
3. Run `python scripts/render_readme.py` locally (regenerates the README table)
4. Open a PR with both changed files

## 3. Automated X search (maintainer-run)
A scheduled GitHub Action searches X for hiring-related posts matching tracked cities/keywords and opens a PR adding candidates to `jobs_pending_review.yaml`. These are **never auto-published** — a maintainer reviews the raw tweet text, fills in the missing fields (role, city, type), and manually moves confirmed entries into `jobs.yaml`.

## Why not LinkedIn automation?
LinkedIn has no public API for reading feed posts, and scraping violates their Terms of Service (accounts doing this get banned, including via headless-browser tools). LinkedIn listings are submitted manually via Issue — if you see one, submit it.

## Data format (`jobs.yaml`)
```yaml
- company: "Company Name"
  role: "Job Title"
  city: "City"
  type: "Full-time | Part-time | Contract | Internship | Freelance"
  apply_link: "https://..."
  source: "manual | x_search"
  posted_date: "YYYY-MM-DD"
```
