# Prerequisites

* Rstudio
* Install the distill package using "install.packages('distill')"
* Sufficient privileges in the GitHub repo
* You will also need to create a GitHub token if you want to commit changes from within Rstudio.: https://stackoverflow.com/questions/66065099/how-to-update-github-authentification-token-on-rstudio-to-match-the-new-policy
* In Rstudio, create a new project from GitHub via File > Version Control > Git. Use https://github.com/jackvanschaik/nlp_team as the Repository URL.


# Overview

The website is created with an R package called distill. Distill allows you to easily create website from preformatted templates using a combination or R code, markdown code, HTML, javascript and css. You can change the website by editing the configuration files (.yml file), the web pages (.Rmd files), the theme (theme_1.css), or any other auxiallary files that you need (e.g., images file).

The documentation on https://rstudio.github.io/distill/website.html tells you almost everything you need to know. To preview the website you've put together you can use the "Build Website" button in Rstudio's build tab or use the following line: rmarkdown::render_site(encoding = 'UTF-8'), and you can view the html files. Once you are satisified with your changes, commit to the GitHub repo and the website will be available in the deployment: https://jackvanschaik.github.io/nlp_team/


# _site.yml 

This is the main configuration file for the site. You can change the css theme or more likely change the available pages in the navbar. The .htmls here should have matching Rmds in the root directory.

# theme_1.css

Css file to be used for formatting across the site.

# *.Rmd

There are the main files that you will be editing, since these get rendered into .html files. The top part is yaml where you can change the title of the site like so:

---
title: "Page name etc"
---

You can add R code chunks like this:

```{r}
print(2 + 2)
```

There is usually a setup chunk at top that determines how following chunks are dealt with:

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = FALSE)
```

You can use plain text or html outside of code chunks. So you can include inline linkes and whatnot:

The main page is <a href="https://jackvanschaik.github.io/nlp_team/index.html"> here </a>

Furthermore, you can use Markdown as documented here: https://raw.githubusercontent.com/rstudio/cheatsheets/main/rmarkdown.pdf, for example you can create headers of various sizes

# Header 1
## Header 2
### Header 3 etc

and 
* bullet
* points
