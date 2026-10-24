# PathFinder

**Rising Rookies · Domain 1 · SDG 4: Quality Education**

PathFinder helps students and career switchers turn a synthetic skills profile into explainable role matches and a source-linked introductory learning plan.

> **Submission status: review draft.** The public prototype works, but the team GitHub URL, pitch video, actual Replit use, RunPod evidence/applicability, and API Premium sponsor integration remain unverified or incomplete. The current application uses deterministic rules; it does not run a language model or a trained forecasting model. Do not claim that the project is submission-ready until the missing requirements are genuinely completed.

## Team Information

| Field | Details |
| --- | --- |
| Team name | Rising Rookies |
| Project name | PathFinder |
| Selected domain | Domain 1 — Aiversecity Future-Ready Workforce |
| Selected SDG track | **SDG 4 — Quality Education** |
| Primary SDG targets | 4.4: relevant technical and vocational skills; 4.3: access to affordable learning |
| Supporting goals | SDG 8, 9, 13 and 16, depending on the selected pathway |
| Team leader | LIN ZIRUI |
| Leader email | 1094184601@qq.com |
| University | Xiamen University Malaysia |
| Number of members | 5 |

## Project and Submission Links

| Resource | Link or current status |
| --- | --- |
| **Live prototype / demo** | **https://futurepath-workforce-radar.spryhaven13.chatgpt.site/** |
| Public team GitHub repository | **PENDING — add the team's actual public repository URL** |
| Team Replit project | **PENDING — add the actual project URL from the team's own account** |
| Replit deployment | **PENDING — no Replit deployment has been evidenced** |
| Pitch / demonstration video | **PENDING — add the actual accessible YouTube URL** |
| Pitch deck | [Pitch deck PDF](submission/SDC2026_RisingRookies_PitchDeck.pdf) |
| Preliminary submission | [Official-template proposal PDF](submission/SDC2026_RisingRookies_Preliminary.pdf) |
| Technical and tools declaration | [Declaration PDF](submission/SDC2026_RisingRookies_TechDeclaration.pdf) |
| Replit proof of use | [Current draft status page](submission/SDC2026_RisingRookies_Replit_POU.pdf) — **not valid proof of use** |
| RunPod proof of use | [Current applicability/status statement](submission/SDC2026_RisingRookies_Runpod_POU.pdf) — **not proof of actual use** |
| RunPod endpoint | None used in the current prototype; required evidence/applicability must be resolved |
| API Premium sponsor integration | **PENDING — no integration or supporting evidence is established** |

The linked PDFs are review drafts. Replace incomplete declarations and evidence pages with completed, truthful versions before submitting. A local draft file or prepared configuration does not establish platform usage.

## Problem

Learners face a practical question: **what should I learn next as AI changes work?** A list of current skills does not explain which roles may fit, what foundations are missing, or which learning activity is a useful first step.

PathFinder focuses on university and TVET learners, fresh graduates and career switchers exploring technical roles. It makes the evidence, assumptions and skill gaps visible so that a person can decide which direction to explore.

The prototype uses an international, Europe-heavy job sample. It does not measure the whole Malaysian labour market or predict individual hiring outcomes.

## Solution and Implemented Features

| Feature | Current behaviour |
| --- | --- |
| Skills profile intake | Fixed fictional personas, skill checkboxes, career interests and available weekly study hours |
| Updatable signal layer | Manual refresh of public job and AI-discussion feeds, with source links, publication dates and retrieval time |
| Explainable role matching | Five curated role pathways with a score out of 100, component breakdown and foundational skill gaps |
| Personalised learning pathway | Missing skills become ordered introductory activities with resource links, estimated hours and total weeks |
| SDG mapping | Every role and skill connects to SDG 4 and relevant application goals, with an explanation |
| Handling uncertainty | Moderate and fast adoption scenarios expose different scoring assumptions |
| Evidence fallback | Validated public/synthetic JSON import when live feeds are unavailable |
| Learner control | Target-role selection, browser-local milestones and a downloadable JSON plan |

**Not implemented:** runtime LLM integration, a trained AI forecasting model, continuous background monitoring, a backend learner database, real CV processing, team-wide HR analytics or recruitment integration. Planned extensions must not be presented as deployed features.

## How to Run the Project

### Option 1: Open the Public Prototype

1. Open https://futurepath-workforce-radar.spryhaven13.chatgpt.site/.
2. Select **My skills profile**.
3. Use a fictional persona and save the skill selections.
4. Open **Future skills radar** to inspect the dated evidence and choose a scenario.
5. In **Role matches**, choose **Build plan** for a target role.
6. Inspect **My learning pathway**, **SDG impact**, and **Sources & method**.

No local installation or API key is needed to use the current public prototype.

### Option 2: Run Locally

**Requirement:** Python 3. The local server uses the Python standard library only; no `pip` packages are required for runtime.

Download or clone the **actual team repository**, then open the project directory containing `README.md`, `dist/`, and `src/`. Do not run the command from inside `dist/` or from inside a ZIP archive.

Windows:

```powershell
py src/main.py
```

If the Python launcher is unavailable but `python` works:

```powershell
python src/main.py
```

macOS / Linux:

```bash
python3 src/main.py
```

Expected terminal output:

```text
PathFinder serving on port 3000
```

Open **http://localhost:3000/**. Keep the terminal running; use **Ctrl+C** to stop it.

To use another port in Windows PowerShell:

```powershell
$env:PORT = "3001"
py src/main.py
```

Then open **http://localhost:3001/**. A localhost address is for your own computer and is not a public sharing link.

### Option 3: Run in the Team's Replit Account

Replit support is **prepared, not evidenced as completed**.

1. Import the actual source into the team's own Replit project.
2. Set the root to the directory containing `dist/`, `src/`, and `.replit`.
3. Use the included run configuration:

```bash
python3 src/main.py
```

4. Verify the application in the project preview. The server listens on `0.0.0.0`, using `PORT` when supplied or port `3000` by default.
5. If publishing a Replit deployment, obtain its real external URL and test access while signed out.
6. Add the real Replit project/deployment URL above and replace the draft proof page with genuine account-owned evidence.

The current runtime requires no AI API key or RunPod endpoint. Do not add invented credentials or mark a planned Replit run as completed.

## Demonstration Walkthrough

Use this reproducible fictional profile:

| Input | Value |
| --- | --- |
| Persona | Alex |
| Background | University student |
| Skills | Python, Circuit analysis, Communication |
| Career interest | Automation & engineering |
| Experience | 0 |
| Weekly study time | 5 hours |
| Scenario | Moderate |
| Target role | Automation Engineer |

1. Save the profile. The target has one listed foundational gap: **Automation**.
2. Open its learning pathway. It contains **32 estimated study hours**, which becomes **7 weeks** at five hours per week: `ceil(32 / 5)`.
3. Inspect the learning reference and practice task. This is an introductory plan, not a professional qualification.
4. Mark a milestone complete and reload to check browser-local persistence.
5. Inspect SDG 4 and the role's other goal links.
6. Use **Export plan** to download `PathFinder-learning-plan.json`.

### Show That Updated Evidence Changes Recommendations

1. Keep the profile and scenario above unchanged.
2. In **Future skills radar**, expand **Import updated public or synthetic signals (JSON)** and import [`fixtures/A.json`](fixtures/A.json).
3. Check the Automation Engineer score: **73/100**.
4. Import [`fixtures/B.json`](fixtures/B.json) and check again: **76/100**.
5. With **Synthetic demonstration** selected, the Python sample direction changes from **Declining** to **Rising**.
6. Do not refresh public feeds between these two imports. Refresh afterward to restore public inputs.

Both files contain deliberately synthetic records. Their `example.org` URLs identify fictional examples; they are not factual job postings. Updating evidence can change scores without necessarily changing the order of every role.

## Technical Architecture

| Layer | Implementation |
| --- | --- |
| Interface | HTML5, CSS3, browser JavaScript |
| Recommendation logic | Deterministic JavaScript in `dist/core.js` |
| Application interactions | Forms, navigation, feed requests and import/export in `dist/app.js` |
| External data | Arbeitnow public job API; Hacker News Search by Algolia |
| Storage | Browser `localStorage` for synthetic selections, evidence and progress |
| Local / Replit server | Python 3 `http.server` through `src/main.py` |
| Current public hosting | ChatGPT Sites / OpenAI-managed static hosting on Cloudflare |
| Runtime AI / GPU | None |
| Application database | None |

The browser validates and deduplicates dated metadata, counts skill keywords separately by source, calculates role scores, identifies missing foundations, orders learning resources, and explains SDG contributions. Updating a source or importing data recalculates the outputs. No background process runs when the page is closed.

### Matching Method

| Scenario | Skills | Interest | Signals | Additional assumption |
| --- | --- | --- | --- | --- |
| Moderate | Up to 65 | Up to 20 | Up to 15 | Equal skill priority |
| Fast | Up to 55 | Up to 20 | Up to 25 | Machine learning, Automation and AI ethics priority: 1.5 |

The interest component is 20 when the selected interest matches the role category, otherwise zero. Skill coverage and signal relevance use the relevant skill priorities.

Signal relevance averages skill keyword prevalence inside each source. Jobs receive 70% and AI discussions 30% of the source weight; available sources are reweighted when one is missing. Synthetic imports use synthetic records only for matching. No signals means zero signal points, not invented data or extra points elsewhere.

Direction comparisons use earlier and later publication-date groups **within one source**, with at least five records in each group. A missing keyword is not evidence of skill obsolescence. Scores are exploratory indices, not hiring probabilities.

## Overall Project Structure

| Path | Purpose |
| --- | --- |
| `README.md` | Project description, links and reproduction instructions |
| `dist/index.html` | Interface, styles and navigation |
| `dist/app.js` | UI behaviour, feeds, local state and import/export |
| `dist/core.js` | Record validation, matching, trend comparison and learning order |
| `src/main.py` | Standard-library local / Replit static server |
| `tests/core.test.cjs` | Core behavioural checks |
| `fixtures/A.json`, `fixtures/B.json` | Explicitly synthetic update demonstrations |
| `docs/TEST_REPORT.md` | Verification record and remaining limits |
| `docs/submission_answers.json` | Editable bounded-answer text used in submission drafts |
| `docs/team_fields.json` | Team information and pending confirmations |
| `submission/` | Proposal, declaration, slides and platform-evidence documents |
| `.replit` | Prepared Replit run configuration |
| `.env.example` | Optional local port setting; no secret required |
| `requirements.txt` | Notes that runtime uses only the Python standard library |
| `LICENSE` | Apache License 2.0 |
| `NOTICE` | Attribution and development-assistance disclosure |

Upload the actual source folders as well as this README and the submission documents. Uploading only a README and a hosted link does not provide the source code shown in the tutorial.

## How We Use Replit

**Current verified status: actual team-account use has not been evidenced.**

The repository contains a Python static server and `.replit` configuration so the team can run the same application on Replit. The observed public deployment is on ChatGPT Sites, not Replit.

Before submission, the team must genuinely use Replit, describe what it did, provide the real project/deployment URL, and supply the required screenshot evidence. The supplied file below is currently a draft status page:

- [Replit proof/status PDF](submission/SDC2026_RisingRookies_Replit_POU.pdf)

The uploaded files tutorial shows examples such as an application deployed on Replit or AI-credit usage. Use genuine evidence from the team's account and remove exposed secrets. A configuration file or a statement of future intent is not proof.

## How We Use RunPod

**Current verified status: none used. No GPU or model workload runs in this prototype.**

The uploaded tutorials explicitly request RunPod usage information and a proof PDF, with examples of a pod/serverless endpoint running a model or GPU usage and billing. The earlier orientation described the RunPod requirement in relation to GPU work. The team must resolve applicability with the organizer rather than assuming that no GPU work automatically waives the tutorial's requirement.

- [RunPod applicability/status PDF](submission/SDC2026_RisingRookies_Runpod_POU.pdf)

Do not describe this draft statement as GPU usage evidence. If RunPod is used, replace it with actual workload details, pod or endpoint ID, GPU type, runtime, and screenshots without credentials. Add the real model/API/service usage to the technical declaration.

## API Premium Sponsor Integration

**Current status: not implemented or evidenced.**

The uploaded GitHub submission tutorial shows a required submission-page confirmation that the project integrates the API Premium sponsor's technology, describing it as mandatory for both rounds. The current public metadata APIs are not claimed to satisfy that sponsor requirement, and this README does not assert eligibility.

Before checking that confirmation, the team must identify the applicable sponsor technology from official instructions, implement the actual required integration, verify it, and declare its purpose and evidence. Update this section and the Technical Tools Declaration afterward. Do not check a sponsor-use confirmation on the basis of this draft alone.

## Verification

Node.js 20 or later is needed only for the optional developer checks, not for ordinary browser use or the Python static server.

Run from the repository root:

```bash
node --check dist/app.js
node --check dist/core.js
node tests/core.test.cjs
```

The behavioural tests cover baseline scoring, evidence and scenario effects, skill gaps, bounds, source separation, sample-size guards, keyword boundaries, safe import URLs/dates, duplicate records, learning order and duration, and synthetic A/B updates.

These software checks do not establish user impact, unbiased recommendations, Malaysian representativeness, platform usage, team ownership or competition eligibility. See [the verification record](docs/TEST_REPORT.md).

## Data Sources and Learning References

| Resource | Purpose | Important limitation / attribution |
| --- | --- | --- |
| [Arbeitnow API information](https://www.arbeitnow.com/blog/job-board-api) | Public job title, tag, date and link metadata | Europe-heavy; provider/publisher rights apply |
| [HN Search by Algolia](https://hn.algolia.com/api) | AI-discussion title, date and link metadata | Discussion proxy, not verified research or labour-market demand |
| [O*NET® OnLine](https://www.onetonline.org/) | Occupational reference links | U.S. Department of Labor, Employment and Training Administration; see [content licence](https://www.onetonline.org/help/license) |
| [UN SDG 4](https://sdgs.un.org/goals/goal4) | Learning and skills contribution framework | Goal mapping expresses potential contributions, not measured outcomes |
| Kaggle Learn, Google ML Crash Course, Arduino Learn, OpenLearn, Microsoft Excel help, UN CC:e-Learn, All About Circuits and Elements of AI | Introductory learning references | Provider terms apply; some links lead to catalogues; certificates or optional services may cost extra |

O*NET® OnLine references are attributed to USDOL/ETA under CC BY 4.0, subject to the source's exceptions. Skill subsets, scores and learning estimates are project-specific simplifications. USDOL/ETA has not endorsed or tested them. See [NOTICE](NOTICE).

Public API access does not imply an unrestricted dataset redistribution licence. The app retains title/tag/date/link metadata, not full job descriptions or HN author fields. The team must verify usage rights and references before certifying the declaration.

## Privacy and Human Control

- Use fictional personas and public or synthetic evidence only. Do not upload real CVs or private learner data.
- Skills, progress and signal metadata stay in the current browser's `localStorage` until reset or browser deletion. They do not automatically sync across users or devices.
- Feed requests contain no profile fields and omit credentials and referrers. Providers still receive normal connection metadata; hosting services may keep normal logs.
- No profile is sent to an AI service. The current app has no learner backend, hiring decision system or runtime AI model.
- Age, gender, ethnicity and university prestige are not scoring inputs. Empirical fairness has not been established.
- The learner chooses the role and whether to follow a plan. Course hours are introductory estimates, not qualification or employment guarantees.

## AI-Assisted Development Disclosure

OpenAI ChatGPT / Codex provided **major** assistance with code, interface design, revisions, tests, document drafting and this README. The exact underlying model identifier was not exposed in the workflow and is not guessed. Development assistance is different from embedding an AI model in the running application.

The registered team must review, adapt, understand and take responsibility for the work. This README does not certify original team authorship, workshop attendance, prior-work ownership or employment-related IP status. Add any other tools, models, datasets or sponsor resources the team actually used to the declaration.

## Challenges and Next Steps

Current challenges include limited regional coverage, keyword ambiguity, short time windows, source outages and the gap between a deterministic baseline and the domain's AI-powered ambition.

Planned work includes evaluating better Malaysian sources and a declared, tested skill-classification model constrained to a verified catalogue. Sponsor integration and required platform evidence are separate outstanding tasks. These are plans, not completed capabilities.

## Submission Checklist

- [x] Team name, project name, Domain 1 and SDG 4 identified in this README.
- [x] Existing public prototype URL included.
- [x] Startup instructions and actual project structure documented.
- [x] Current algorithm and major AI-development assistance disclosed.
- [ ] Upload the actual application source and supporting files to the team repository.
- [ ] Add the real public team GitHub URL and confirm signed-out access.
- [ ] Add the genuine Replit project/deployment URL and replace its draft proof with actual screenshots.
- [ ] Resolve RunPod applicability and provide actual evidence if required; do not submit a status note as proof of use.
- [ ] Complete and evidence the applicable API Premium sponsor integration before confirming it on the submission form.
- [ ] Add an accessible YouTube pitch/demo URL and check the official duration requirements.
- [ ] Finish the official proposal and Technical Tools Declaration, including missing confirmations and a genuine signature.
- [ ] Include the real `LICENSE` file containing Apache License 2.0 and retain third-party notices.
- [ ] Follow official instructions for committee repository access and preserve genuine commit history.
- [ ] Confirm all members' workshops, originality/IP answers and understanding of the core features.
- [ ] Test every relative file link and external submission link after uploading.
- [ ] Complete the official submission before the deadline and follow the latest organizer instructions.

The supplied earlier orientation gives the preliminary deadline as **25 October 2026, 07:59:59 MYT (UTC+8)**. Confirm the latest official announcements and Terms & Conditions. The new video includes a submission-page preview; copying the organizer's sample repository URL does not submit this team's work. Use the team's actual public repository and never make an untrue sponsor-use confirmation.

## Licence

Project code is supplied under the [Apache License 2.0](LICENSE), subject to the team's confirmation that it has the rights to submit and license the work. Third-party datasets, references and services retain their own terms. See [NOTICE](NOTICE).

## Tutorial References

This README follows the visible instructions in the team-supplied videos:

- `SDC_GitHub_Submission_Guide.mp4`, approximately 00:35–00:45: README content checklist; approximately 01:00–01:10: public repository submission and sponsor confirmation.
- `SDC_Submission_Files_Tutorial.mp4`, approximately 00:15–00:25: submission folder; approximately 01:10–01:25: platform proof examples; approximately 01:25–01:40: README fields.

The videos' example names, links and usage screenshots belong to the tutorial and are not evidence of this team's activity.
