# Summer Open And Reproducible Research (SOAR²)

This repository contains the source code for the Summer Open And Reproducible Research (SOAR²) [program website](https://ucsb-library-research-data-services.github.io/SOAR2/), built with Jekyll and published through GitHub Pages. The 2026 program took place at UC Santa Barbara from September 21–23, 2026.
 
SOAR² is a three-day program for undergraduate students designed to demystify the hidden curriculum of research and introduce open and reproducible practices as fundamental parts of the research process. During the 2026 program, students participated in interactive modules, hands-on activities, field trips to campus research facilities, and a keynote talk. They learned about reproducible workflows, data management, research transparency, and open sharing. The 2026 SOAR² program was organized by the [UCSB Library](https://www.library.ucsb.edu/) in collaboration with [the Office of Undergraduate Research & Creative Activities (URCA)](https://urca.ucsb.edu/), with funding support from [the Open Research Community Accelerator](https://www.orcaopen.org/).

This repository now serves two purposes:

* Preserve the final 2026 program website, including instructor profiles, session descriptions, curriculum materials, and resources
* Provide a reusable starting point for a future SOAR² offering or a similar program

<br/>

## Acknowledgement and Citation
This repository was originally cloned from [druckmann-lab/math-tools](https://github.com/druckmann-lab/math-tools), which was derived from [kazemnejad/jekyll-course-website-template](https://github.com/kazemnejad/jekyll-course-website-template), itself based on [svmiller/course-website](https://github.com/svmiller/course-website). Full citations to these repositories are included below.

* Druckmann Lab. *Course website for Introduction to Mathematical Tools in Neuroscience (NEPR 209).* GitHub, 2026. https://github.com/druckmann-lab/math-tools
* Kazemnejad, A. *Jekyll Course Website Template.* GitHub, 2020. https://github.com/kazemnejad/jekyll-course-website-template
* Miller, S and Chhatre, V. *Steve's No-Good-Very-Bad Course Website Jekyll Template.* GitHub, 2019. https://github.com/svmiller/course-website

<br/>


## Repository structure

### Pages and subpages

* `index.md`: Homepage content. The `home` layout adds announcements, features, schedule cards, and organizer information.
* `sessions.md`: Program and session overview. Individual session pages are generated from `_lectures/`
* `instructors.md`: Instructor landing page. Profiles are generated from `_instructors/`
* `resources.md`: Resources landing page. Detailed resource pages are stored in `subpages/`
* `about.md`: Background, goals, and general program information
* [not published] `schedule.md`: legacy schedule page, currently not published
* [not published or in use] `assignments.md`: legacy assignments page, currently not published or used


### Content collections

* `_announcements/`: Time-sensitive messages displayed on the homepage
* `_lectures/`: Module and special-session metadata, content, schedule-card settings, and individual session URLs. The reader-facing term is **Sessions**, but the inherited code uses `lectures`
* `_instructors/`: Instructor profiles referenced by instructor IDs in session files
* `_events/`: Scheduled events used by the inherited schedule system
* [not in use] `_assignments/`: Inherited sample assignment content; not currently used


### Data and navigation

- `_config.yml`: Program name, dates, publishing URL, repository information, collections, and other site-wide settings
- `_data/nav.yml`: Main navigation, dropdown links, labels, and ordering
- `_data/feature.yml`: Feature cards displayed on the homepage
- `_data/entity.yml`: Organizer and funder names, links, logos, and alt text
- `_data/program_representatives.yml`: Participant information for the Pasta & Possibilities session


### Supporting pages, assets, and presentation

- `subpages/`: Supporting resource pages and the internal instructor guidance page. Public URLs are set by each file’s `permalink`
- `_images/`: Program graphics, instructor photos, collaborator images, module icons, and resource images
- `session_materials/`: slides, datasets, PDFs, and other downloadable session files
- `_layouts/`: Page templates
- `_includes/`: Reusable page components
- `_css/` and `_sass/`: Site styling
- `website_snapshots/`: archived PDF and PNG captures from earlier stages of the website

<br/>


## How to maintain this website? (for RDS folks)

This site is built with Jekyll. Most updates can be made by editing Markdown, YAML, images, and other static files without changing the underlying layouts.


### How the site is assembled?

- Files in `_lectures/` generate the session cards and individual session pages. Their `permalink` values determine the public URLs under `/sessions/`.
- Session files reference instructors through `lead_instructors` IDs. Each ID must match an `instructor_id` in `_instructors/`.
- Homepage schedule cards are controlled by fields such as `home_schedule`, `home_schedule_order`, `home_day_label`, and `home_card_description` in `_lectures/`.
- Homepage announcements come from `_announcements/` and are controlled by `published` and `announcement_order`.
- Navigation is independent of publication. Removing a page from `_data/nav.yml` hides its menu link but does not necessarily make its URL inaccessible.
- To prevent Jekyll from generating a page, add `published: false` to its front matter.



### Common update workflow

| Goal | Task |
|------|------|
| Change the program name, dates, publishing URL or other site-wide settings | Edit `_config.yml` |
| Show, hide, reorder, or rename nav items | Edit `_data/nav.yml` |
| Revise homepage content | Edit `index.md` |
| Revise homepage feature cards | `_data/feature.yml` |
| Update organizer or funder information | `_data/entity.yml` |
| Add or revise a homepage announcement | `_announcements/` |
| Add or revise an instructor profile | `_instructors/` and the corresponding image in `_images/instructors/` |
| Add or revise a session | `_lectures/` |
| Change homepage session ordering or summaries | The relevant file in `_lectures/` |
| Add session slides, handouts, or datasets | `session_materials/`, followed by links from the relevant session file |
| Update Pasta & Possibilities participants | `_data/program_representatives.yml` |
| Update student resources | `resources.md` and the relevant files in `subpages/` |
| Change page structure or reusable components | `_layouts/` and `_includes/` |
| Change colors, typography, spacing, or responsive behavior | `_css/` and `_sass/` |



### Additional project-specific notes

* Some pages are intentionally omitted from `_data/nav.yml` until they are ready to be publicly promoted. Removing a page from navigation does not necessarily make its URL inaccessible.
* The reader-facing section is called **Sessions**, but it still uses the `lectures` collection and related layouts internally.
* The `_assignments/` collection and assignments page are inherited from the original course template and are not currently used.
* `session_materials/from-template/` and some files under `session_materials/temp/` are examples or working materials rather than final program content. Review them before reusing the repository.
* Some module information appears both in overview cards and expanded session content within the same `_lectures/` file. Review both when making changes.
* Pages with time-sensitive opportunity information should include a visible “current as of” date and should be reviewed before being republished.
* If the repo name or publishing location changes, update both `url` and `baseurl` in `_config.yml`. This applies when working with Forks and Pull Requests.

<br/>


## How to reuse this repository and deploy on GitHub Pages?
1. Fork or clone this repository.
2. Open `_config.yml`.
   1. Update `url` field according to your GitHub account (e.g., `https://<your-github-username>.github.io/`).
   2. Update `baseurl` field according to your repository's name (e.g., `/soar2`).
   3. Commit and push your changes.
3. Go to your repository's settings (`https://github.com/<your-github-username>/<your-repo-name>/settings`).
4. On GitHub Pages section, choose source to be your main branch, and enable Github Pages.
5. You are now ready to go! Start customizing your website.

For more information and tips about how to manage, update, and deploy this repository, see README of [kazemnejad/jekyll-course-website-template](https://github.com/kazemnejad/jekyll-course-website-template)


<br/>

## Generative AI usage

Codex (GPT-5.5 Medium Intelligence; 5.6 Sol Light) was used to navigate the template repository, develop certain website functionalities (e.g., cards), troubleshoot code, and draft this README file. All published content was reviewed and edited by the project maintainers to ensure accuracy.
