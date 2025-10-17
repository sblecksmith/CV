# CV-template

A template to create a Data Driven CV or Resume using R, YAML, LaTeX, and Github Actions

## Install and Setup

#### Repository

1. Create your own CV or Resume by selecting the green button in the upper right-hand corner of [the repository](https://github.com/ccbaumler/CV-template)
	- Select `Use this template`	
	- Select `Create a new repository`

2. Give your new repository a name like `CV` and `Create repository`

This will allow you to make changes locally to the Rmarkdown scripts in the `scripts` directory and update the `data.r` file in the `data` directory.

#### Local

1. Clone the repository to your local computer

```
git clone git@github.com:<username>/CV.git
```

2. Install the packages necessary for the scripts to run:
> vitae, tibble, magrittr, here, readr, glue

<details>

<summary>A Helpful Script</summary>

```
# List of all the packages used
packages <- c('vitae'     # The CV's LaTeX Template
             ,'tibble'    # Data structure for tribbles
             ,'magrittr'  # The Pipe %>%
             ,'here'      # Relative File Paths
             ,'readr'     # Data Loading
             ,'glue'      # String Manipulation
            )


# Find and install any packages not yet installed
installed <- rownames(installed.packages())
to_install <- setdiff(packages, installed)
if (length(to_install) > 0) {
  install.packages(to_install)
}
```

</details>

3. Add your changes to the `data/data.r` file and the two rmarkdown scripts in `scripts/` 
	- `scripts/awesome-cv/awesome-cv.Rmd` writes out a `PDF` file.
	- `scripts/markdowncv/markdowncv.Rmd` writes out an `HTML` file.

4. `Knit` the documents to see the changes

#### Github Actions


1. In your local repo, replace `your-name` with your actual name by changing `your-name` to `<your-actual-name>`
```
git grep 'your-name' .github/workflows/build_CV_action.yaml | xargs sed -i 's/your-name/<your-actual-name>/g'
```
> `git grep 'your-name' .github/workflows/build_CV_action.yaml`. Add `-l` to list every file in the repository that contains the string `your-name`.
> `xargs sed -i 's/your-name/<your-actual-name>/g'` will replace the `your-name` text with `<your-actual-name>` text for every file listed by the previous `git grep` command.


2. In Github, for a stand-alone, static webpage of your CV/resume
`Settings` > `Pages` > `Branch` > `main` > `/docs` > `Save`

3. The GitHub actions require permission to push changes to the files. Do so by navigating to:
`Settings` > `Actions` > `General` > `Workflow permissions` > `Read and write permissions`

## What is the motivation of this project?

"If I do it three time or more, it should be automated"
- C. Titus Brown

Resume and CV construction can be a tedious endevour when using industry standard software like Microsoft Word. Add a new bullet point or volunteer experience, watch the entire document shift in unsightly ways.

This template follows the rule of destroying obstacles with overwhelming force. In this case, standardizing the resume/CV writing process with very powerful statistical software! :tada:

The goal of this repo is to eliminate the tedium of fine-tuning resume/CV documents whenever new information is added. Now, whenever and wherever you are, you will be able to update this document by updating the `data/data.r` file. The repo will do the rest.

## How to Contribute

1. Clone this repo
2. Make some changes
3. Create a pull request
4. Request a review when completed

## Authors

Colton Baumler

[![UC Davis Email](https://img.shields.io/badge/UC_Davis-Email-blue?style=for-the-badge&colorA=blue&colorB=gold)](mailto:ccbaumler@ucdavis.edu) <a href="mailto:ccbaumler@gmail.com"><img src="https://img.shields.io/badge/gmail-%23DD0031.svg?&style=for-the-badge&logo=gmail&logoColor=white"/></a>

