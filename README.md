# The Alief Audit

A two-minute self-audit that asks one question: **do you treat AI the way you think about it?**

A companion to the Medium article *AI Consciousness: The Alief Thesis* by Ed Daniels.

Standing on a glass floor over the Grand Canyon, you *believe* the glass will hold you. Your legs are not so sure. The philosopher Tamar Gendler called that gut-level conviction an **alief**. This audit measures what you believe about AI, how you treat it, and the gap between the two.

## What it does

- 14 questions in three parts: what you believe (4), how you treat it (9), and a paramedic's "run report" (1).
- Produces two scores from 0 to 100, **Belief** and **Treatment**, plus the **gap** between them (Treatment minus Belief).
- Places you on a four-quadrant map:

|                               | Treats AI as a tool | Treats AI as a someone |
|-------------------------------|---------------------|------------------------|
| **Believes it is not conscious** | Skeptic             | Alief                  |
| **Believes it may be conscious** | Colleague           | Companion              |

- Shows an interpretation of your quadrant and gap, up to three "tells" drawn from specific answers, and your run report verdict.
- Marks where the article's author landed, for comparison.

## Privacy

Everything runs in your browser. No login, no server, no cookies, no storage, no analytics. Nothing you answer leaves the page.

## Scoring

Each answer carries a value from 0 to 100. Belief is the average of Part 1 (the 0 to 10 slider counts as 0 to 100). Treatment is the average of Part 2. The run report is reported separately and is not scored. The quadrant boundary is 50 on each axis. The values are in the `Q` array near the top of the script in `index.html`, so anyone can inspect or change them.

This is a mirror, not a diagnosis. It is not a validated psychological instrument. The scoring reflects one writer's judgment about which habits signal belief and which signal alief.

## Deploy on GitHub Pages

1. Create a public repository (for example `alief-audit`) and add `index.html` and this `README.md`.
2. In the repository, go to **Settings → Pages**, set the source to the `main` branch and the root folder, and save.
3. The audit will be live at `https://<your-username>.github.io/alief-audit/`.
4. In `index.html`, set the `href` of the link with `id="articleLink"` to the published article URL.

## License

Choose a license before publishing (MIT is a common choice for small open projects).
