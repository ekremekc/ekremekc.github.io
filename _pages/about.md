---
permalink: /
title: "Personal Website"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

Our research is centered around the optimization for engineering applications. We aim to use [Open Source Software (OSS)](https://en.wikipedia.org/wiki/Open-source_software) in order to push the boundaries of the computer. We aim to apply certain optimization techniques and tools on wide spectrum of engineering problems such as:
* acoustics/thermoacoustics
* heat transfer
* biomedicals
* structures
* fluids

We use different numerical toolkits to address engineering optimization problems. See [Interests](https://ekremekc.github.io/portfolio/) page to find out what we do.

<!-- # Diary -->

<style>
  .calendar-container {
    width: 100%;
    max-width: 800px; /* Optional: constrain on larger screens */
    margin: 0 auto;
  }

  .calendar-container iframe {
    width: 100%;
    height: 700px; /* or adjust as needed */
    border: 0;
  }

  @media (max-width: 768px) {
    .calendar-container iframe {
      height: 1000px; /* taller on small screens to show more hours */
    }
  }
</style>

<!-- <div class="calendar-container">
  <iframe 
    src="https://calendar.google.com/calendar/embed?height=600&wkst=1&ctz=Asia%2FRiyadh&mode=week&showPrint=0&showCalendars=0&hl=en&src=YzQ4OTdhNTM4ZDY5YWFhOTllOGE5M2E2ZDMwODZmYTYwMmVlMzFiOTkzZTMwY2MxNzNiYzQyYjVjNGZlYWQwNEBncm91cC5jYWxlbmRhci5nb29nbGUuY29t&src=ZW4tZ2Iuc2F1ZGlhcmFiaWFuI2hvbGlkYXlAZ3JvdXAudi5jYWxlbmRhci5nb29nbGUuY29t&color=%23d81b60&color=%234285f4" 
    frameborder="0" 
    scrolling="no">
  </iframe>
</div> -->

# Diary (experimental) 

<div class="calendar-container">
<iframe src="https://calendar.zoho.com/zc/ui/embed/#calendar=zz08011230fdfdd64458c7611a7c276581419f1de17414472fcfc49ed0efee24f89b7845feceee687941986bd711da0d00c42b384a&title=Academic&type=1&language=en&timezone=Europe%2FIstanbul&showTitle=1&showTimezone=1&startingDayOfWeek=0&timeFormat=0&view=work&showDetail=0&theme=3&showAttendee=0&showSwitchingViews=1&expandAllday=1&eventColorType=light&startHour=8&endHour=17" title="Academic" frameBorder="0" scrolling="no"></iframe>
</div>

## Meeting form (experimental)
<div class="calendar-container">
<iframe src="https://calendar.zoho.com/eventreqForm/zz08011230fdfdd64458c7611a7c276581419f1de17414472fcfc49ed0efee24f89b7845feceee687941986bd711da0d00c42b384a?theme=0&l=en&tz=Europe%2FIstanbul"></iframe>
<div class="calendar-container">


<!-- Getting started
======
1. Register a GitHub account if you don't have one and confirm your e-mail (required!)
1. Fork [this repository](https://github.com/academicpages/academicpages.github.io) by clicking the "fork" button in the top right. 
1. Go to the repository's settings (rightmost item in the tabs that start with "Code", should be below "Unwatch"). Rename the repository "[your GitHub username].github.io", which will also be your website's URL.
1. Set site-wide configuration and create content & metadata (see below -- also see [this set of diffs](http://archive.is/3TPas) showing what files were changed to set up [an example site](https://getorg-testacct.github.io) for a user with the username "getorg-testacct")
1. Upload any files (like PDFs, .zip files, etc.) to the files/ directory. They will appear at https://[your GitHub username].github.io/files/example.pdf.  
1. Check status by going to the repository settings, in the "GitHub pages" section

Site-wide configuration
------
The main configuration file for the site is in the base directory in [_config.yml](https://github.com/academicpages/academicpages.github.io/blob/master/_config.yml), which defines the content in the sidebars and other site-wide features. You will need to replace the default variables with ones about yourself and your site's github repository. The configuration file for the top menu is in [_data/navigation.yml](https://github.com/academicpages/academicpages.github.io/blob/master/_data/navigation.yml). For example, if you don't have a portfolio or blog posts, you can remove those items from that navigation.yml file to remove them from the header. 

Create content & metadata
------
For site content, there is one markdown file for each type of content, which are stored in directories like _publications, _talks, _posts, _teaching, or _pages. For example, each talk is a markdown file in the [_talks directory](https://github.com/academicpages/academicpages.github.io/tree/master/_talks). At the top of each markdown file is structured data in YAML about the talk, which the theme will parse to do lots of cool stuff. The same structured data about a talk is used to generate the list of talks on the [Talks page](https://academicpages.github.io/talks), each [individual page](https://academicpages.github.io/talks/2012-03-01-talk-1) for specific talks, the talks section for the [CV page](https://academicpages.github.io/cv), and the [map of places you've given a talk](https://academicpages.github.io/talkmap.html) (if you run this [python file](https://github.com/academicpages/academicpages.github.io/blob/master/talkmap.py) or [Jupyter notebook](https://github.com/academicpages/academicpages.github.io/blob/master/talkmap.ipynb), which creates the HTML for the map based on the contents of the _talks directory).

**Markdown generator**

I have also created [a set of Jupyter notebooks](https://github.com/academicpages/academicpages.github.io/tree/master/markdown_generator
) that converts a CSV containing structured data about talks or presentations into individual markdown files that will be properly formatted for the Academic Pages template. The sample CSVs in that directory are the ones I used to create my own personal website at stuartgeiger.com. My usual workflow is that I keep a spreadsheet of my publications and talks, then run the code in these notebooks to generate the markdown files, then commit and push them to the GitHub repository.

How to edit your site's GitHub repository
------
Many people use a git client to create files on their local computer and then push them to GitHub's servers. If you are not familiar with git, you can directly edit these configuration and markdown files directly in the github.com interface. Navigate to a file (like [this one](https://github.com/academicpages/academicpages.github.io/blob/master/_talks/2012-03-01-talk-1.md) and click the pencil icon in the top right of the content preview (to the right of the "Raw | Blame | History" buttons). You can delete a file by clicking the trashcan icon to the right of the pencil icon. You can also create new files or upload files by navigating to a directory and clicking the "Create new file" or "Upload files" buttons. 

Example: editing a markdown file for a talk
![Editing a markdown file for a talk](/images/editing-talk.png)

For more info
------
More info about configuring Academic Pages can be found in [the guide](https://academicpages.github.io/markdown/). The [guides for the Minimal Mistakes theme](https://mmistakes.github.io/minimal-mistakes/docs/configuration/) (which this theme was forked from) might also be helpful. -->