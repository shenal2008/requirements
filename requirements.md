# Stepwise Careers-  Requirements and User Stories

Status: draft for review

Owner: Shenal (Planning Leader)

Reviewer: Sanuth

Last updated: 5 November 2026



---

## 1. Purpose

Stepwise Careers helps final-year computing students at NSBM work out which IT roles suit them, what skills they are missing, and what to do about it before they graduate. Career advisers see the same picture across a whole class. Employers and alumni post local openings.

The project runs over two semesters. A working app with the core features is due in December 2026. The finished product is due in May 2027.


---
## 2. Scope

**In scope.** 25 to 30 IT roles. Three user types. Skills matching, CV building and feedback, learning plans, job market trends for several countries, class-level analysis for advisers, and local job postings.

**Out of scope, by decision.** Roles outside IT. A chatbot or conversational assistant. A social feed or messaging between students. Hosting or recommending specific courses. Any automated collection from Sri Lankan job websites. A web version the app is Android and iPhone only.


---
## 3. Users

| User type | Who they are | What they need |
| --- | --- | --- |
| Student | Final-year NSBM computing student | Know which roles fit, what is missing, and what to do next |
| Adviser | NSBM career adviser or academic staff | See where a class stands without seeing individuals |
| Employer / alumni | Local employers and NSBM graduates | Post openings to students who match them |

An unregistered visitor can browse roles and market data but cannot save anything.

---

## 4. Functional requirements

Each requirement traces to a card on the project board.

### 4.1 Accounts and roles

- **FR-01** A student can create an account with an email address and password, and sign in on any device.
- **FR-02** The app works without an account. Anything saved locally is kept and merged in when the student later signs in.
- **FR-03** An adviser account is created by an administrator, not by self-registration.
- **FR-04** An employer or alumni account self-registers but cannot post until approved.
- **FR-05** A student can join one class using a short code given by their adviser, and can leave it.
- **FR-06** Joining a class asks for consent first and says exactly what the adviser will and will not see.
- **FR-07** A student can delete their account from inside the app. Deletion removes the account and all data attached to it.
- **FR-08** A student sees only their own data. An adviser sees only their own classes. These rules are enforced in the database.
- **FR-09** A user can reset their password through a verified email address.

### 4.2 Qualification profile and CV

- **FR-10** A student can enter their qualifications: degree and year of study, modules with grades, projects, internships and work experience, certificates, and languages.
- **FR-11** The app builds a formatted CV from the profile and exports it as a PDF.
- **FR-12** At least two CV layouts are available.
- **FR-13** A student can alternatively paste an existing CV as plain text.
- **FR-14** The app scores a CV against a published rubric and lists specific fixes: missing sections, weak opening verbs, achievements with no figures, length, and coverage of the target role's skills.
- **FR-15** Every rubric rule is documented with its reasoning.
- **FR-16** A student can produce a version of their CV aimed at a chosen role, with matching skills and relevant projects brought forward.
- **FR-17** The app never invents experience and never rewrites the student's wording into claims they did not make.
- **FR-18** A student can connect a GitHub account. The app reads public repositories only: languages, topics, recency, and the share of commits that are theirs.
- **FR-19** A student can disconnect GitHub at any time. The app never writes to their account.

### 4.3 Skills

- **FR-20** The app identifies candidate skills from a CV and shows each one with the sentence it came from.
- **FR-21** The student confirms or rejects every suggested skill, and can add skills the app missed.
- **FR-22** Personal details email addresses, links, and phone numbers  are removed on the device before any text leaves the phone.
- **FR-23** CV text is used only for CV analysis and skills extraction. Original CV text is not stored on the server and can be removed from the device by the student at any time.
- **FR-24** A keyword method is used when the server cannot be reached, and the app says which method produced the result.
- **FR-25** A student can verify a skill by taking a short test. Verified skills are marked differently from self-claimed skills throughout the app.
- **FR-26** Skills are identified internally by their dictionary identifier, so the same skill is never counted twice under two names.
- **FR-27** A student can manually edit or remove skills from their profile at any time
- **FR-28**Skills shall indicate their source: self-declared, CV-derived, GitHub-derived, module-derived, or verified.
- **FR-29** The student can search and browse the skills dictionary and add skills manually.

### 4.4 Roles and matching

- **FR-30** The app covers between 25 and 30 IT roles, each linked to its skills from the European skills dictionary.
- **FR-31** Roles are ranked by match score. Roles with no matching skills are hidden.
- **FR-32** Match scores shall give greater weight to essential skills than optional skills. The scoring method shall be documented and applied consistently across all roles. percentage.
- **FR-33** Each ranked role shows matched skills, missing skills, and a fit band: strong, possible, stretch, or poor.
- **FR-34** Each fit band comes with a plain sentence explaining it, naming the skills that decide it.
- **FR-35** When a student chooses a role that comes out as a poor fit, the app suggests the closest better-fitting role and explains what makes it closer. The student's own choice is never blocked.
- **FR-36** A student can paste a job advert and see the skill gap for that specific advert.
- **FR-37** Advert text is treated exactly like CV text: personal details removed on the device, nothing stored.
- **FR-38** A student can see where a role leads over three and five years, with the skills and pay at each step, labelled as typical paths rather than promises.
- **FR-39** A student can compare two or more roles side-by-side, including required skills, salary information, and market demand data where available.

### 4.5 Learning

- **FR-40** Missing skills for a target role become steps spread over the months until graduation, essential skills first.
- **FR-41** Steps are ordered by prerequisite, using the relationships in the skills dictionary. A student is never asked to learn something that depends on a skill further down their own plan.
- **FR-42** Learning-plan steps shall be distributed as evenly as possible across the months remaining until graduation.
- **FR-43** When that works out at more than three steps a month, the plan warns that there is not enough time for every skill and marks optional skills as "if time allows".
- **FR-44** The plan gives no time estimates for learning a skill.
- **FR-45** Each step shows the skill's description and search links to Coursera and edX. The app never selects, ranks, hosts or endorses a course.
- **FR-46** Ticking a step adds the skill to the student's profile and is saved.
- **FR-47** The plan rebuilds itself when steps are ticked, the target role changes, or a skill is verified.
- **FR-48** Where a mapped upcoming module teaches a missing skill, the plan shows it as a step the student is already taking.
- **FR-49** A student can see which electives would close the biggest gaps towards their target role.

### 4.6 Market data

- **FR-50** For each role, the app shows the Australian online job-ad trend over time.
- **FR-51** Forecasts cover six months ahead, with optimistic, baseline and pessimistic ranges.
- **FR-52** Ranges are built from the role's own past forecast errors and are labelled as ranges, not predictions.
- **FR-53** A role needs at least 36 continuous months of data for scenarios. Below that, past data is shown with "Not enough data for scenarios".
- **FR-54** Gaps in the source data are never filled in or estimated.
- **FR-55** New Zealand figures are annual percentage change only, with no forecast.
- **FR-56** The app also covers the United Kingdom, Singapore and Canada where published data allows.
- **FR-57** Every figure is labelled with its country, its period, and its source.
- **FR-58** Where a role's figures come from a shared occupation group rather than its own, the app says so wherever a number appears.
- **FR-59** Sri Lanka has no published occupation-level demand data. The app shows no Sri Lankan demand figure. Local opportunities come only from employer and alumni postings and from students.

### 4.7 Adviser

- **FR-60** An adviser sees the most common skill gaps in a class, the most popular target roles, and how far students are through their plans.
- **FR-61** An adviser sees totals only, never an individual student's details.
- **FR-62** Nothing is shown for a class until at least five students in it have data. This is enforced in the database.
- **FR-63** An adviser can compare what a class holds against what the market asks for, role by role.
- **FR-64** An adviser can see the spread of readiness scores across a class.
- **FR-65** An adviser can export a class report for the department.
- **FR-66** An adviser can view changes in class readiness and skill-gap trends over time.
- **FR-67** An adviser can identify the most commonly missing skills across a class.
- **FR-68** An adviser can filter results by intake, degree programme, or graduation year.
- **FR-69** Adviser dashboards refresh automatically when new student data is available.

### 4.8 Employer and alumni

- **FR-70** An employer or alumnus can post an opening: role, skills wanted, location, closing date, and how to apply.
- **FR-71** A posting is not visible to students until approved by an adviser or administrator.
- **FR-72** Postings expire automatically after their closing date.
- **FR-73** Students see postings matched against their own skill profile.
- **FR-74** An employer or alumnus can edit or withdraw their own postings before the closing date.
- **FR-75** An employer or alumnus can withdraw a posting at any time.
- **FR-76** Students can report inappropriate or misleading po stings.
- **FR-77** Reported postings are hidden until reviewed by an administrator.
- **FR-78** Employers can view how many students have viewed a posting.
- **FR-79** Employers receive a notification when a posting is approved or rejected.

### 4.9 Job search

- **FR-80** A student can save roles and track applications through stages: saved, applied, interview, offer, rejected.
- **FR-81** An application records its closing date, notes, and which CV version was sent.
- **FR-82** A student can practise interview questions for a target role, generated from that role's essential skills, and rate their own confidence.
- **FR-83** Weak areas from interview practice feed back into the learning plan.
- **FR-84** A student has a readiness score based on skill coverage, CV quality, learning-plan progress, and interview preparation. The contribution of each component shall be visible to the student.
- **FR-85** A student can opt in to find classmates with complementary skills, visible only to their own class, and can opt out at any time.
- **FR-86** Students can record interview dates and receive reminders.
- **FR-87** Students can record outcomes of applications for later review.
- **FR-88** Students can view application statistics, including success rates and interview rates.
- **FR-89** A student can export their application history.


### 4.10 Platform and administration

- **FR-90** The app runs on Android and iPhone.
- **FR-91** The interface is available in English, Sinhala and Tamil. Skill and role names stay in English, and the app says why.
- **FR-92** A student can choose which notifications they receive, and can turn them all off.
- **FR-93** Notifications cover plan steps due, application closing dates, and an optional weekly summary.
- **FR-94** An administrator can add or retire roles, correct skill links, approve employer accounts and trigger a data refresh, without a code change.
- **FR-95** Every administrative action is written to an activity log with who did it and when.

---

## 5. Non-functional requirements

- **NFR-01** No figure shown in the app is typed by hand. Every number is computed by a script from a published source.
- **NFR-02** Where data is missing the app says "Data not available". It never shows a zero or an estimate in place of a missing figure.
- **NFR-03** Stored data is limited to: email address, graduation date, confirmed skill identifiers, target roles, plan progress, applications, class membership and notification settings.
- **NFR-04** Data is kept until the student deletes their account or the project ends, whichever comes first.
- **NFR-05** All source licences are recorded with the date each source was accessed, and credited in the app.
- **NFR-06** Touch targets are at least 48 points. The app works with large system font sizes and with a screen reader.
- **NFR-07** The app has a light and a dark theme.
- **NFR-08** Main screens open in under two seconds on a mid-range Android phone.
- **NFR-09** The app works offline for everything that does not need the server, and syncs when a connection returns.
- **NFR-10** Tests run automatically on every pull request and must pass before merging.
- **NFR-11** No credentials, keys or personal data are committed to the repository.
- **NFR-12** The skills matching is evaluated against a labelled test set, and the result is published with the project whether it improves on the simpler method or not.
- **NFR-13** All communication between the mobile application and server shall use HTTPS encryption.
- **NFR-14** User passwords shall be stored as secure hashed values and never in plain text.
- **NFR-15** A backup of server data shall be created at least once per day.
- **NFR-16** The system shall support at least 500 registered student accounts.
- **NFR-17** The application shall recover gracefully from temporary network failures without losing user data.

---

## 6. Evaluation

- At least 30 sample CVs labelled independently by two team members, with a third settling disagreements.
- At least 10 sample student profiles with an agreed expected top three roles, checked against an adviser's judgement where possible.
- Forecast accuracy measured on 12 months of data held back from model selection, reporting both coverage and average error.
- Usability testing with at least five students: task success, time taken, and a standard usability questionnaire.
- A measured before-and-after comparison for any change to the skills matching.

---

## 7. Open questions / Design decisions

- Generated CV PDFs are not stored. They are rebuilt from saved profile information whenever required.
- Fit-band thresholds:
- Strong: 80–100%
- Possible: 60–79%
- Stretch: 40–59%
- Poor: Below 40%
- A score of 70% or higher counts as verifying a skill.
- Module-to-skill mappings are created by the project team and reviewed by an NSBM lecturer or academic adviser before publication.
- Approval for usability testing shall be confirmed with the project supervisor and any relevant NSBM research or ethics authority before participant recruitment.
- Expired employer postings are retained for 12 months for reporting and audit purposes and are then permanently removed.

--- 
## 7. Design decisions

### 7.1 Generated CV storage
Generated CV PDF files are not stored on the server. The PDF is rebuilt from the student's saved profile information whenever a new export is requested.

### 7.2 Role match thresholds
Role fit bands are defined as:

- Strong: 80%–100%
- Possible: 60%–79%
- Stretch: 40%–59%
- Poor: Below 40%

### 7.3 Skill verification pass mark
A score of 70% or higher in a skill verification test is required for a skill to be marked as verified.

### 7.4 Module-to-skill mapping
Mappings between NSBM modules and skills are created by the project team and reviewed by a lecturer or academic adviser before being used in the application.

### 7.5 User-testing approval
Usability testing shall be approved by the project supervisor and must follow any NSBM research or ethics requirements that apply to student projects.

### 7.6 Expired job postings
Employer and alumni job postings remain archived for 12 months after their closing date for reporting and audit purposes before permanent deletion.


---
## 8. Data sources

| Source | What it provides | Licence |
| --- | --- | --- |
| European skills and occupations dictionary (ESCO v1.2.1) | Role and skill definitions, essential and optional skills | Free to use with credit |
| Australian Internet Vacancy Index | Monthly online job-ad counts by occupation | CC BY 4.0 |
| New Zealand Jobs Online | Quarterly annual percentage change | CC BY 4.0 |
| Australian occupation profiles | Median full-time weekly earnings | CC BY 4.0 |
| United Kingdom, Singapore, Canada statistics | Vacancy and employment figures | To be confirmed per source |

Coursera and edX are search link targets only. No data is taken from them.
