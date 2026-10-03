# The Alief Audit

A two-minute self-audit that asks one question: **do you treat AI the way you think about it?**

A companion to the Medium article *AI Consciousness: The Alief Thesis* by Ed Daniels.

Standing on a glass floor over the Grand Canyon, you *believe* the glass will hold you. Your legs are not so sure. The philosopher Tamar Gendler called that gut-level conviction an **alief**. This audit measures what you believe about AI, how you treat it, and the gap between the two.

## What it does

- 14 questions, numbered "Question 1 of 14" and so on, in three groups: what you believe about AI consciousness (4), how you treat AI (9), and a paramedic's level-of-consciousness check (1).
- The last question puts the reader in a paramedic's shoes: treat your AI as a patient, ask it who it is, where it is, and when the conversation is taking place, and record what you would write on the run report (alert and oriented; alert but confused; responds to voice/text only; or "this isn't a patient").
- Produces two scores from 0 to 100, **Belief** and **Treatment**, plus the **gap** between them (Treatment minus Belief).
- Places you on a four-quadrant map:

|                                  | Treats AI as a tool | Treats AI as a someone |
|----------------------------------|---------------------|------------------------|
| **Believes it is not conscious** | Skeptic             | Alief                  |
| **Believes it may be conscious** | Colleague           | Companion              |

- Shows an interpretation of your quadrant and gap, up to three "tells" drawn from specific answers, and your run report verdict. The on-screen map also marks where the article's author landed (belief 89, treatment 38), for comparison.
- Makes a **run report card**: a one-page PNG with your result, an optional name, and only your own dot. You can download it, copy it, or (on phones and tablets) share it straight to Messages, email and other apps. It is designed for passing around and for group discussions.
- Works on phones, tablets and computers.

## Privacy

Everything runs in your browser. No login, no cookies, no analytics. The name on the card never leaves your device.

When results collection is switched on (see below), respondents are offered an opt-in at the end: **"I agree to add my anonymous result."** The page explains that the author plans to compile the results and publish the findings to the public. Only if they click it does the page send their two scores, quadrant, and 14 multiple-choice answers, plus the date. It sends no name, no email, and nothing that identifies the person or device. Google Apps Script does not expose visitors' IP addresses to the script. The browser remembers that it has already submitted, to discourage duplicates.

## Scoring

Each answer carries a value from 0 to 100. Belief is the average of questions 1 to 4 (the 0 to 10 slider counts as 0 to 100). Treatment is the average of questions 5 to 13. The run report is reported separately and is not scored. The quadrant boundary is 50 on each axis. The values are in the `Q` array near the top of the script in `index.html`, so anyone can inspect or change them.

This is a mirror, not a diagnosis. It is not a validated psychological instrument. The scoring reflects one writer's judgment about which habits signal belief and which signal alief.

## Files

- `index.html`: the whole audit, in one file.
- `Code.gs`: the Google Apps Script that receives opted-in results and writes them to a Google Sheet. It is **not** served by GitHub Pages; it is pasted into Google Apps Script (below). Keeping it in the repo lets anyone see exactly what is collected.

## Setting up results collection (one time, about 10 minutes)

1. In Google Drive, create a new Google Sheet, for example **Alief Audit Results**.
2. In the sheet, open **Extensions → Apps Script**. Delete the sample code, paste in all of `Code.gs`, and click **Save**.
3. Optional: choose the `setup` function in the toolbar and click **Run** to create the **Results** tab and header row now. Google will ask you to authorize the script; approve it. (The tab is also created automatically on the first submission.)
4. Click **Deploy → New deployment**. Click the gear next to "Select type" and choose **Web app**. Set **Execute as: Me** and **Who has access: Anyone**. Click **Deploy** and authorize if asked.
5. Copy the **Web app URL** (it ends in `/exec`).
6. In `index.html`, find `const SUBMIT_URL = '';` near the top of the script and paste the URL between the quotes. Commit the change to GitHub.
7. Test it: take the audit on the live site, click **Add my anonymous result**, and check that a row appears in the Results tab.

Until `SUBMIT_URL` is filled in, the opt-in box stays hidden, the privacy wording on the page says simply that nothing is sent anywhere, and the audit works exactly as before.

**If you later edit `Code.gs`**, use **Deploy → Manage deployments → Edit → Version: New version** so the same URL keeps working. Creating a brand-new deployment gives a new URL, which you would then have to paste into `index.html` again.

**Answer key:** the Results tab stores each answer as short text (for example "Always" or "Collaborator"), so it can be read and charted directly. If you change the questions in `index.html`, update the `KEY` list in `Code.gs` to match and bump `VERSION` in `index.html`.

## Deploy on GitHub Pages

1. Create a public repository (for example `alief-audit`) and add `index.html`, `Code.gs` and this `README.md` at the top level.
2. In the repository, go to **Settings → Pages**, set the source to *Deploy from a branch*, the `main` branch and `/ (root)`, and save.
3. The audit will be live at `https://<your-username>.github.io/alief-audit/`.
4. In `index.html`, set the `href` of the link with `id="articleLink"` to the published article URL.

## License

Choose a license before publishing (MIT is a common choice for small open projects).

## Version history

- **Version 2 (October 3, 2026).** Wording changes after reader testing, because "inner experience" was less familiar to readers than "conscious": question 1 now asks how likely it is that today's AI is conscious, with the subtitle "In other words, do you believe AI is conscious?"; question 3 now asks about scientists announcing that AI "is conscious"; question 14 was rewritten as a paramedic's level-of-consciousness check with clearer answer choices. Part labels were removed from the question screens. Scoring is unchanged. Submissions record `Version` 2, so results can be separated from version 1 test runs.
- **Version 1 (October 1, 2026).** First release.
