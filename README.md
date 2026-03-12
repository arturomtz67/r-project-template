# R Project Structure Template

This repository provides an example structure for an **R project focused on data analysis.** It is intended as a starting point for organizing scripts, data, outputs, and documentation in a clear and reproducible way.

This template is a **work in progress** and shows my current experience and understanding of good practices for structuring R-based data analysis projects. The goal is to provide a practical guide and tips that can help keep projects organized and easier to reproduce.

You can use this template as a guide when starting new projects, but it is not meant to be rigid. Feel free to adapt, modify, or simplify the structure depending on the needs of your project, team, or workflow.

Suggestions, improvements, and feedback are very appreciated.


# Project Title

Provide a title that clearly reflects the purpose of your project.

Add a short description explaining what the repository contains and what the project aims to accomplish.

## Project Overview

Wrtite and overview of the project, for example:
The goal of this project is to investigate..... 

Include:
- Research question
- Motivation
- Context

The analysis workflow tipically follows these main steps:
1.  Data import
2.  Data cleaning
3.  Missing data imputation
4.  Descriptive analyses
5.  Statistical analyses
6.  Visualization and reporting


## Requirements / packages

List the dependcies or packages needed to reporoduce/use this project. For example:
This project uses `renv` to manage package versions. To run the project on a new machine:

```{r}
install.packages("renv") 
renv::restore()
```

`renv::restore()` installs the package versions recorded in `renv.lock`, so the project uses the same R package environment it was developed with. 

For collaboration, you should commit the following files:
-   `renv.lock`
-   `.Rprofile`
-   `renv/activate.R`

After restoring the environment, open the project in RStudio/Positron and run the analysis pipeline using `targets` for example.


## Project Structure
Below is an example of a recommended project structure. Folder names can be adapted, but they should remain **clear and self-explanatory.**

-   **R:** contains all R scripts used in the analysis pipeline. Scripts are organized by analysis stage (data import, cleaning, imputation, descriptive analysis, statistical analysis, and visualization)
  
-   **input or data:** contains the data frames or files (images, files) that are input to the project.

    -   `raw/` original datasets as received from the source.

    -   `processed/` cleaned or transformed datasets ready for analysis.

    -   `samples/` smaller sample datasets used for testing or development.
      
    -   `images/`

-   **output:** contains all generated outputs from the analyses, including figures, tables, and intermediate results such as imputation outputs.

-   **reports:** contains Quarto reports documenting the analyses. Typically each report directory includes:

    -   `drafts/` working versions of reports.

    -   `final/` finalized reports used for presentation or publication.

-   **results:** contains final publication-oriented outputs of the project, including:

    -   `manuscript/` main paper or report files.
    -   `supplementary/` supplementary materials and appendices.
    -   `figures/`finalized figures prepared for reporting or publication.
    -   `presentation/` – presentation slides and communication materials.
    
-   **README file:** documentation describing the project
-   **.gitigonore:** specifies files that should not be tracked by Git


After explaining the folders content show the tree of your project with this code (in terminal tree -L 3 or in the conslose install.packages("fs"), then run fs::dir_tree(recurse = 3)) and copy the output in a text cell in the README file.

 ``` text
.
├── R
│   ├── 01_import
│   ├── 02_clean
│   ├── 03_impute
│   ├── 04_descriptive
│   ├── 05_analysis
│   └── 06_visualization
├── input
│   ├── processed
│   ├── raw
│   └── sample
├── output
│   ├── figures
│   ├── imputation
│   └── tables
├── renv.lock
├── reports
│   ├── drafts
│   └── final
├── results
│   ├── manuscript
│   ├── supplementary
│   ├── figures
│   └── presentation
├── README.md
└── .gitignore
 
```

## Data

Describe the dataset used in the project. Include:

-   Where the data comes from what it contains size/variables.
-   Full names and definitions (spell out abbreviated words) of column headings for tabular data.
-   Units of measurement.
-   Definitions for codes or symbols used to record missing data
-   Specialized formats or abbreviations used

## Methodology
Describe the analytical approach used in the project, examples include:
-   Data preprocessing steps
-   Statistical models
-   

## Results
Mention the key results of the project. This may include:

-   Important results
-   Figures
-   Tables
-   Interpretations


## Reproducibility

Mention how to run the project to reproduce the analysis, for example:

This project uses `renv` to manage package versions and `targets` to manage the analytical workflow.

To reproduce the project on a new machine/computer:

```{r}
install.packages("renv")
renv::restore()

install.packages("targets") # only needed if not already restored
targets::tar_make()
```

## Name of author(s) and/or paper 
Mention the name(s) of the author(s) that contrtibuted to this project/repo or paper, affiliations of the authors, email of the person resposible of the repo.

If applicable also include the title of the the paper. 

## License
Specify the license used for this repository.

## Sources
Here is a list of sources I found usefull to make keep a project tidy.
-   [Productive R workflow](https://www.productive-r-workflow.com/)

      
