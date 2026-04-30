# Summer Open And Reproducible Research (SOAR²)

Website source code for the Summer Open And Reproducible Research (SOAR²) Camp, to be held on the UCSB campus from September 21–23, 2026.
 
SOAR² is a three-day program for undergraduate students that aims to demystify the hidden curriculum of research and introduce open and reproducible practices as fundamental to conducting research. During these three days, students will participate in interactive modules, hands-on activities, field trips to campus research facilities, and your keynote talk. Students will learn about reproducible workflows, data management, research transparency, and open sharing. SOAR² is organized by the [UCSB Library](https://www.library.ucsb.edu/) in collaboration with [the Office of Undergraduate Research & Creative Activities (URCA)](https://urca.ucsb.edu/), with funding support from [the Open Research Community Accelerator](https://www.orcaopen.org/).

This repository contains a Jekyll site used to publish program information, modules, instructors, and other related content for SOAR².

<br/>

## Acknowledgement and Citation
This repo was originally cloned from [druckmann-lab/math-tools](https://github.com/druckmann-lab/math-tools), which was derived from [kazemnejad/jekyll-course-website-template](https://github.com/kazemnejad/jekyll-course-website-template), which built upon [svmiller/course-website](https://github.com/svmiller/course-website). Full citations to these repositories are included below

* Druckmann Lab. *Course website for Introduction to Mathematical Tools in Neuroscience (NEPR 209).* GitHub, 2026. https://github.com/druckmann-lab/math-tools
* Kazemnejad, A. *Jekyll Course Website Template.* GitHub, 2020. https://github.com/kazemnejad/jekyll-course-website-template
* Miller, S and Chhatre, V. *Steve's No-Good-Very-Bad Course Website Jekyll Template.* GitHub, 2019. https://github.com/svmiller/course-website

<br/>

## How to maintain this website (for RDS folks)

This site is built with Jekyll and organized so that most updates can be made by editing Markdown, YAML, and static files rather than changing HTML.

### Repository structure

#### Top level pages

* `_config.yml`: site-wide settings, such as title, dates, url, etc
* `index.md`: Home page content
* `instructors.md`: Instructors landing page
* `lectures.md`: Modules landing page
* [hidden from nav] `about.md`: About page
* [hidden from nav] `assignments.md`: Assignments page
* [hidden from nav] `schedule.md`: Schedule landing page


#### Content collections

* `_announcements/`: homepage announcements
* `_events/`: scheduled events (e.g., field trip, keynote lecture)
* `_instructors/`: instructor profiles
* `_lectures/`: individual module entry
* [not used] `_assignments/`: assignment content


#### Layout and presentation

* `_css/`: compiled/entry styles
* `_includes/`: reusable snippets
* `_images/`: site images and logos
* `_layouts/`: page templates
* `_sass/`: Sass partials
* `static_files/`: downloadable PDFs and other assets

#### Data files

* `_data/nav.yml`: top navigation menu
* `_data/entity.yml`: organizer and funder logos/links


### Common update workflow

* To program name, timing, or site-wide metadata: edit `_config.yml`
* To show, hide, or change nav items: edit `_data/nav.yml`
* To update homepage text: edit `index.md`
* To add or revise a module: create or edit a file in `_lectures/`
* To add or revise an instructor profile: create or edit a file in `_instructors/`
* To post a new homepage announcement to the Update box: create a file in `_announcements/`


### Project-specific notes

* Some pages are intentionally hidden from navigation until the program timeline requires them
* For SOAR², "Modules" is backed by the `lectures` collection under the hood. The page is named `lectures.md`, but its permalink is `/modules/`.
* The `_assignments/` collection is present but not actively used
* Homepage organizer/funder sections are driven by _data/entity.yml and _layouts/home.html
* If the repo name or publish location changes, update `url` and `baseurl` in `_config.yml`


<br/>

## How to reuse this repo and deploy on GitHub Pages
1. Fork or clone this repository.
2. Open `_config.yml`.
   1. Update `url` field according to your GitHub account (e.g., `https://<your-github-username>.github.io/`).
   2. Update `baseurl` field according to your repository's name (e.g., `/soar2`).
   3. Commit and push your changes.
3. Go to your repository's settings (`https://github.com/<your-github-username>/<your-repo-name>/settings`).
4. On GitHub Pages section, choose source to be your master branch, and enable Github Pages.
5. You are now ready to go! Start customizing your website.

For more information and tips about how to manage, update, and deploy this repository, see README of [kazemnejad/jekyll-course-website-template](https://github.com/kazemnejad/jekyll-course-website-template)



