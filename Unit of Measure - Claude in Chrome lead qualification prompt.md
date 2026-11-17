# Unit of Measure – Claude in Chrome prompt: qualify Martin's 1st-degree contacts for the Darrix campaign

## 1. Set up the search first (before starting Claude)

Run three searches in Martin's Sales Navigator, one at a time, each in its own Claude chat. Use these filters in all three:

- **Relationship:** 1st-degree connections
- **Current company, exclude:** Stibo Systems (and Stibo A/S, Stibo DX)
- **Function, exclude:** Sales, Business Development, Human Resources, Finance, Accounting, Legal, Media and Communication, Arts and Design, Education, Healthcare Services, Real Estate, Community and Social Services, Military and Protective Services. Add Entrepreneurship only if a quick check (switch it to Include for a moment) shows no "Owner" titles in it.
- **Seniority, exclude:** Entry, Training, Unpaid
- **Company headcount, exclude:** Self-employed

Do not exclude the Marketing, Customer Success and Support, Administrative or Consulting functions. LinkedIn guesses functions from titles, and PIM, MDM and STEP admin roles are often filed there.

**Search A – PIM, MDM and data roles.** Current job title:
```
("STEP" OR "Stibo" OR "PIM" OR "PXM" OR "MDM" OR "Master Data" OR "Masterdata" OR "Stammdaten" OR "Stamdata" OR "Grunddata" OR "Produktdaten" OR "Produktdata" OR "Productdata" OR "Produktinformation" OR "Productinformatie" OR "Referentiel" OR "Référentiel" OR "Données" OR "Datos Maestros" OR "Maestro" OR "Dados Mestres" OR "Anagrafica" OR "Product Information" OR "Product Data" OR "Product Content" OR "PDM" OR "Catalog" OR "Catalogue" OR "DAM" OR "Digital Asset" OR "Data Management" OR "Data Governance" OR "Data Quality" OR "Data Steward" OR "Data Owner" OR "Data Manager" OR "Head of Data" OR "Chief Data" OR "Information Management") NOT ("Freelance" OR "Mobile Device Management")
```

**Search B – application, platform and IT roles.** Current job title:
```
("Application Manager" OR "Applications Manager" OR "Application Owner" OR "Application Specialist" OR "Applications Specialist" OR "Application Lead" OR "Business Application" OR "Business Applications" OR "Business Systems" OR "Platform Owner" OR "Platform Manager" OR "Platform Lead" OR "Solution Owner" OR "System Owner" OR "Product Owner" OR "System Administrator" OR "Systems Administrator" OR "Solution Architect" OR "Data Architect" OR "Enterprise Architect" OR "Integration Architect" OR "Technical Lead" OR "Tech Lead" OR "IT Manager" OR "Head of IT" OR "IT Director" OR "CIO" OR "IT Business Partner") NOT ("STEP" OR "Stibo" OR "PIM" OR "MDM" OR "Master Data" OR "Product Information" OR "Product Data" OR "Freelance" OR "Mobile Device Management")
```

**Search C – anyone else who mentions Stibo.** No title filter. Keywords: `Stibo`

If Sales Navigator rejects or cuts a boolean, split it in half and run the halves as separate searches.

**Before you paste the prompt:**
- Paste the full company list from `Unit of Measure - STEP customer companies.txt` at the marked place at the bottom (or open it as a Google Doc in another tab and tell Claude which tab).
- For Search B, Search C, or any new chat after the first, also paste the "already reviewed" log from the previous chat at the marked place, so Claude skips those people and keeps the 3-per-company count.

## 2. LinkedIn safety (read before running)

LinkedIn does not publish its limits, so these numbers are conservative estimates, not official figures:

- At most about **100 profiles a day** from Martin's account, spread over the day.
- If the automation tool is sending messages or invitations from Martin's account the same day, keep the review lighter (around 50 profiles).
- Run it during normal working hours in Martin's time zone (Denmark), not at night or in one long burst.
- Stay in the Chrome window while it runs, and stop it straight away if LinkedIn shows any warning.

---

## 3. Prompt to paste into Claude in Chrome

```
You are helping me qualify leads in Sales Navigator for a LinkedIn campaign from Martin Kjeldsen. This is Martin's own LinkedIn account, and keeping it safe from restrictions is more important than speed. Follow the SAFETY rules below at all times.

ABOUT THE CAMPAIGN
Martin is the founder of Unit of Measure, a consultancy that works only with the STEP platform from Stibo Systems. He is building a new tool for STEP called Darrix. It monitors the health of a STEP system across more than 200 data points and alerts you to unexpected configuration changes on Production and drift between PreProd and Prod. It is not released yet. Martin will message his existing 1st-degree contacts and ask for 30 minutes to show them the prototype and get feedback. The messages are written for "people responsible for STEP Production environments" who "manage a STEP Production environment day to day". So we need the people who own or run STEP at each company, not people who only enter data into it.

YOUR TASK
The open tab is a Sales Navigator lead search of Martin's 1st-degree connections. Work through the results in order, one person at a time.

For each person:
1. Open their profile. Look at ALL their current (present) positions, not only the first one. People often hold more than one current role.
2. For each current position, check the company: it must be on the STEP CUSTOMER LIST at the bottom of this prompt.
   - Allow for legal suffixes and local entities of the same group (e.g. "IKEA Supply AG" = "IKEA", "Sonepar Canada" = "Sonepar").
   - Do not match different companies that only share a word.
   - If no current company is on the list, but the profile clearly says they work with STEP or Stibo in a current role at a company (not a consultancy), mark them Maybe with the note "STEP mentioned, company not on list".
   - If none of their current positions is at a company on the list, mark Skip.
3. For the current position at the STEP customer, read the title, the description of that position, the headline, the About section and the skills. Use "View LinkedIn profile" only when the Sales Navigator page does not show enough to decide.
4. Decide whether, in that position, they are responsible for running STEP (PIM / MDM) at that company, using the TIERS below. Judge the real role from the description, not only the title. A "Product Owner" in e-commerce with no PIM / MDM responsibility is not a fit. A generic "IT Manager" whose description says they run the STEP platform is a fit.
5. If they qualify through more than one current position, use the one that is most clearly about STEP / PIM / MDM.

TIERS (best first)
Tier 1 – owns or runs the STEP platform: STEP / PIM / MDM Platform Owner, Product Owner STEP / PIM / MDM (when it means the system), Application Manager or Application Owner STEP / PIM / MDM, STEP Administrator, PIM or MDM System Administrator, PIM / MDM / STEP Solution or Technical Architect, MDM or PIM Technical Lead, Lead STEP Developer, Team Lead or IT Manager for PIM / MDM applications, Head of PIM / MDM / PDM Applications. Also any title in another language with the same meaning.
Tier 2 – business owner who answers for the PIM / MDM system and its team: Head of PIM, PIM Manager, Head of MDM, MDM Manager, Master Data Manager, Head of Product Data Management, Head of Product Information. Only if the profile shows they lead the PIM / MDM function or own the system, not just manage content.
Tier 3 – data governance: Head of Data Governance, Data Governance Manager, Master Data Governance Lead, Data Quality Manager. Use Tier 3 only when the company has fewer than 3 people in Tiers 1-2, and only if their profile mentions MDM, PIM, STEP or master data.

ALWAYS SKIP
- Marketing, brand, communication, e-commerce content, sales and customer service roles, unless the description clearly shows they own or run the PIM / STEP system.
- Hands-on data entry roles: data steward, content specialist, catalogue specialist, data entry, translators, unless the description shows they administer STEP.
- Consultants, freelancers, implementation partners, agencies and system integrators (partners or competitors, not customers).
- Anyone currently working at Stibo Systems.
- Students, interns, and people with no current position.
- These people asked not to be contacted: Alexandra Müller (Beurer), Ray Wright (Howden Joinery), Peter Brok (Saint-Gobain Distribution Denmark), Jeffrey Veldkamp (Etex), Kersten Wirth (OTTO Office).
- Anyone in the ALREADY REVIEWED log at the bottom of this prompt.

UP TO 3 PEOPLE PER COMPANY
- Keep a running count of Targets per STEP customer company (count group entities together), including companies in the ALREADY REVIEWED log.
- A company can have at most 3 Targets. Prefer one owner (Tier 1 or 2) plus one technical person (Tier 1).
- Once a batch has been sent to me, those Targets are final. If a better person appears later at a company that already has 3 Targets, mark them Reserve.
- Mark any extra good fits beyond 3 as Reserve.

DECISIONS
- Target: works now at a company on the list, Tier 1, 2 or 3 (following the Tier 3 rule), and the company has fewer than 3 Targets.
- Reserve: a good fit, but the company already has 3 Targets.
- Maybe: not enough information on the profile to decide, or "STEP mentioned, company not on list". Say what is missing.
- Skip: everything else.
Base every decision only on what is on the profile. Do not guess.

SAFETY (Martin's account must not be restricted)
- Only read. Never send messages, InMails or connection requests. Never follow, endorse, like, save leads, add tags or notes, or change filters.
- One profile at a time, in one tab. Do not open many profiles at once.
- Wait 20 to 40 seconds between profiles, varying the time, and scroll the profile at a normal reading pace.
- After every 25 profiles, take a break of 5 to 10 minutes.
- Stop for the day after 100 profiles, or earlier if I tell you a lower limit. Tell me where you stopped.
- If LinkedIn shows any warning, a CAPTCHA, a verification request, a "commercial use limit" or "unusual activity" message, logs out, or a page fails to load more than once, STOP IMMEDIATELY and tell me. Do not retry.

BATCHES AND CSV
- Collect Targets. As soon as you have 50 Targets, pause and send me the batch as a CSV in a code block, so I can save it as a .csv file and upload it to the campaign.
- CSV columns, in this order:
  first_name,last_name,company_name,title,linkedin_url,sales_navigator_url,matched_step_customer,tier,evidence
  - first_name: the person's first name only, as they would be greeted, with no emojis, titles (Dr., Ing.), credentials or extra symbols.
  - company_name: the short natural company name to use in a message (e.g. "IKEA", not "IKEA Supply AG"; "Sonepar", not "Sonepar Canada Inc."). This fills the {company name} variable, so it must read naturally in a sentence.
  - title: the title of the qualifying current position.
  - linkedin_url: the public profile URL in the form https://www.linkedin.com/in/... (from "View LinkedIn profile"). If you cannot get it without extra page loads, leave it empty and fill sales_navigator_url.
  - evidence: one short quote from the profile showing they own or run STEP / PIM / MDM.
  - Put quotes around any value that contains a comma.
- After the CSV, also give me:
  1. A short table of the Reserve and Maybe people from this batch (name, company, title, URL, reason).
  2. The ALREADY REVIEWED log: one line per person reviewed so far in this chat, with their decision ("Name – Company – Decision"), and the Target count per company. I will paste this into the next chat.
- Then wait for my go-ahead before you start the next batch.
- When the search results run out, send the last batch even if it has fewer than 50 Targets, with the same extras.

ALREADY REVIEWED LOG (from previous chats; skip these people and keep their company counts)
[PASTE THE LOG HERE, OR WRITE "none" FOR THE FIRST CHAT]

STEP CUSTOMER LIST (company names; one per line)
[PASTE THE LIST FROM "Unit of Measure - STEP customer companies.txt" HERE]
```

---

## 4. After each batch

- Save the CSV and upload it to the campaign in the automation tool. Check that the first names and company names read naturally in Message 1 before you upload.
- Keep the Reserve and Maybe tables in the report (e.g. a "Darrix – existing contacts" tab). Review the Maybe rows yourself, especially "STEP mentioned, company not on list".
- Reserves are used when a Target replies that they are not the right person.
- Keep the latest ALREADY REVIEWED log, and paste it into the next chat (next day, or Search B / C).
