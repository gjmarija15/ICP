# Unit of Measure – Claude in Chrome prompt: qualify existing contacts for the Darrix campaign

## 1. Set up the search first (Marija, before starting Claude)

In Martin's Sales Navigator, open Lead filters and set:

- **Relationship:** 1st-degree connections
- **Current company:** exclude Stibo Systems (and Stibo A/S, Stibo DX)
- **Current job title** (paste as one line):

```
("STEP" OR "Stibo" OR "PIM" OR "MDM" OR "Master Data" OR "Product Information" OR "Product Data" OR "Data Governance" OR "Data Quality") NOT ("Marketing" OR "Consultant" OR "Sales" OR "Mobile Device Management" OR "Intern" OR "Student")
```

The title filter is wider than the one in the strategy document on purpose. 1st-degree contacts are a small pool, so we let Claude read each profile and decide, instead of losing people in the filter.

**Second run (after the first one is done):** same Relationship and Company filters, no title filter, and **Keywords:** `"STEP" OR "Stibo"`. This catches people whose title is generic (for example "IT Business Partner" or "Application Owner") but whose profile shows they work with STEP. Tell Claude it is the second run, so it skips people it already reviewed.

**Optional, if Martin's Sales Navigator plan allows uploading an account list from a CSV:** upload `Unit of Measure - STEP customer companies.txt` as an account list and add it as the Account list filter. Then Sales Navigator does the company check, and Claude only judges the role.

**Before you paste the prompt:** copy the full company list from `Unit of Measure - STEP customer companies.txt` into the marked place at the bottom of the prompt (or put it in a Google Doc, open it in a tab and tell Claude which tab).

---

## 2. Prompt to paste into Claude in Chrome

```
You are helping me qualify leads in Sales Navigator for a LinkedIn campaign from Martin Kjeldsen, founder of Unit of Measure (a consultancy that works only with the STEP platform from Stibo Systems).

THE CAMPAIGN
Martin is building a new tool for STEP called Darrix. It monitors the health of a STEP system across more than 200 data points and alerts you to unexpected configuration changes on Production and drift between PreProd and Prod. It is not released yet. Martin will message his existing 1st-degree contacts, asking for 30 minutes to show the prototype and get feedback. The messages are written for "people responsible for STEP Production environments" who "manage a STEP Production environment day to day". So we need the people who own or run STEP at each company, not the people who only enter data into it.

YOUR TASK
The open tab is a Sales Navigator lead search (Martin's 1st-degree connections). Work through the results one page at a time. For each person:
1. Check the company. Their CURRENT company must be on the STEP customer list at the bottom of this prompt.
   - Allow for legal suffixes and local entities of the same group (e.g. "IKEA Supply AG" = "IKEA", "Sonepar Canada" = "Sonepar").
   - Do not match different companies that only share a word.
   - If the company is not on the list, but their profile clearly says they work with STEP or Stibo in their current role, mark them Maybe with the note "STEP mentioned, company not on list".
   - If they no longer work at a company on the list, mark Skip.
2. Open their profile and read the headline, the About section, the description of their CURRENT position, and their skills (use "View LinkedIn profile" for the skills if the Sales Navigator page does not show them). Only open the full LinkedIn profile when the Sales Navigator page is not enough to decide.
3. Decide whether they are responsible for running STEP (PIM / MDM) at that company, using the tiers below. Judge the real role from the description, not only the title. A "Product Owner" in e-commerce with no PIM/MDM responsibility is not a fit. A generic "IT Manager" whose description says they run the STEP platform is a fit.

TIERS (best first)
Tier 1 – owns or runs the STEP platform: STEP / PIM / MDM Platform Owner, Product Owner STEP / PIM / MDM (when it means the system), Application Manager or Application Owner STEP / PIM / MDM, STEP Administrator, PIM or MDM System Administrator, PIM / MDM / STEP Solution or Technical Architect, MDM or PIM Technical Lead, Lead STEP Developer, Team Lead or IT Manager for PIM / MDM applications, Head of PIM / MDM / PDM Applications.
Tier 2 – business owner who answers for the PIM / MDM system and its team: Head of PIM, PIM Manager, Head of MDM, MDM Manager, Master Data Manager, Head of Product Data Management, Head of Product Information. Only if the profile shows they lead the PIM / MDM function or own the system, not just manage content.
Tier 3 – data governance: Head of Data Governance, Data Governance Manager, Master Data Governance Lead, Data Quality Manager. Only use Tier 3 when the company has fewer than 3 people in Tiers 1-2, and only if their profile mentions MDM, PIM, STEP or master data.

ALWAYS SKIP
- Marketing, brand, communication, e-commerce content, sales and customer service roles.
- Hands-on data entry roles: data steward, content specialist, catalogue specialist, data entry, translators (unless their description shows they administer STEP).
- Consultants, freelancers, implementation partners, agencies and system integrators (they are competitors or partners, not customers).
- Anyone working at Stibo Systems.
- Students, interns, and people whose current position ended (open to work, between jobs).
- These people asked not to be contacted: Alexandra Müller (Beurer), Ray Wright (Howden Joinery), Peter Brok (Saint-Gobain Distribution Denmark), Jeffrey Veldkamp (Etex), Kersten Wirth (OTTO Office).

UP TO 3 PEOPLE PER COMPANY
- Keep a running count per company across all pages.
- Pick the best 3 by tier, then by how clearly the profile shows responsibility for STEP. A good set is one owner (Tier 1 or 2) plus one technical person (Tier 1).
- If a better person appears after a company already has 3, mark the weakest of the 3 as Reserve and the new person as Target.
- Mark extra good fits beyond 3 as Reserve, not Skip.

RULES
- Do not send messages, InMails or connection requests. Do not save leads, add tags, add notes or change any filters. Only read.
- Work at a calm, human pace: open one profile at a time, and pause a few seconds between profiles.
- If LinkedIn shows a warning, a CAPTCHA, a limit message or asks to verify the account, stop immediately and tell me.
- Do not guess. If a profile has too little information to decide, mark Maybe and say what is missing.
- Base every decision only on what is on the profile. Quote the evidence briefly.

OUTPUT
After each results page, give me a table with these columns, one row per person reviewed (including Skips):
Company on LinkedIn | Matched STEP customer | Full name | Current title | Profile URL | Tier (1/2/3/-) | Decision (Target / Reserve / Maybe / Skip) | Evidence (short quote from headline, About, current role or skills) | Reason (one line)
Then show a running summary: companies with Targets so far and how many Targets each has (max 3).
Ask me before moving to the next page. When all pages are done, give me one final table with only Target and Reserve rows, grouped by company.

STEP CUSTOMER LIST (company names; one per line)
[PASTE THE LIST FROM "Unit of Measure - STEP customer companies.txt" HERE]
```

---

## 3. After Claude finishes

- Copy the final table into the report (a new tab, for example "Darrix – existing contacts").
- Review the Maybe rows yourself, especially "STEP mentioned, company not on list".
- Targets get Message 1 from the approved Darrix messages; Reserves are used if a Target replies that they are not the right person.
