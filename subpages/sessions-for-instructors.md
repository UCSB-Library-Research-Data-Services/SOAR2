---
layout: page
title: "README for Instructors"
permalink: /sessions/for-instructors/
---

_** Note, this page will only be visible on the DEV page. It will be hidden on the [actual SOAR² program website](https://ucsb-library-research-data-services.github.io/SOAR2/) for students._

<br/>

## Module Page Content

Each module page will contain the following section (up for discussion)

* Module Description
* Lead Instructors
* Slides
* Additional Reading (3 max)


<br/>


## Slides

There are two ways that we can display slides directly from the webpage.

**Option 1. Display slides saved as a PDF on GitHub Repo**

PDF should be saved and organized in `session_materials` on GitHub repo. _**This could be good for long-term storage**_. See below as an example.

<iframe
  src="{{ '/session_materials/temp/SOAR2_Slide_Template.pdf' | relative_url }}#view=FitH"
  title="SOAR2 slide template PDF"
  style="
    width: 100%;
    max-width: 100%;
    height: min(65vh, 700px);
    border: 1px solid #ddd;
    display: block;
  ">
</iframe>


<br/>

**Option 2: Display Google Slides directly using a URL**

It's possible to embedd a Google Slide deck via its sharing link (as preview). This option looks better on mobile and _**may be be the better option for temporary access when the program is in session.**_

[//]: Note for website contributor and maintainer:
[//]: For the following lines of code to work, double check permission for Google Slides. Make sure anyone with the link can View.
[//]: Also, replace /view?... with /preview at the end of the Gslide URL

<iframe
  src="https://docs.google.com/presentation/d/1P6EqtzQtA4iatslwDgxd0ZYZF5q4L9Arr8Xrbqw04yQ/preview"                  
  title="SOAR2 flyer for demo purpose"
  style="
    width: 100%;
    max-width: 100%;
    height: min(65vh, 700px);
    border: 1px solid #ddd;
    display: block;
  ">
</iframe>


<br/>


## Code

This website is built with Jekyll. Jekyll will render Markdown, but I don't think it will execute R chunks like a .qmd file? 🤔 Open to suggestions 🙏

We could, however, embed non-running code chunks. See below

```r
library(readr)
library(dplyr)
library(ggplot2)

bw_data <- read_csv("session_materials/temp/motrpac_rat_8wk_bw_data.csv")

bw_summary <- bw_data %>%
  group_by(sex, study_group, timepoint, training_day) %>%
  summarise(wt_mean = mean(weight),
            wt_sd = sd(weight))

ggplot(data = bw_summary, 
       mapping = aes(x = training_day, y = wt_mean, group = study_group, color = study_group)) +
  geom_line() +
  geom_point(size = 2) +
  geom_errorbar(mapping = aes(ymin = wt_mean - wt_sd, ymax = wt_mean + wt_sd), 
                width = 0.5) +
  facet_wrap(~sex, ncol = 1, scales = "free_y") +
  theme_bw() +
  labs(title = "Body weights of rats over 8 week training period (mean +/- sd)",
       x = "Days of training", y = "Body weight (g)", color = "Group")
```


So if we want to share any script with the students and ask them to run it...

- We could have code chunks on a .md file as part of this website (see example above). We'll then ask student to copy and paste into their IDE.
- OR we could create a repo just for that modules, and hyperlink that repo here. Students will only need to pull that module-specific repo and work with it. 
    - This is probably the cleaner option: students don't have to deal with the repo for this website, which has way too much unrelated layers and content...


