# poe: Pathways of Effects Explorer

<!-- badges: start -->

<!-- badges: end -->

## Overview

The `poe` package provides an interactive Shiny User Interface for exploring Pathways of Effects (PoE) diagram models developed by the Canadian Wildlife Service (CWS).

## Requirements

- R \>= 4.1.0
- Quarto (for report generation, installed by default with RStudio)

## Installation

You can install poe from GitHub.

``` r
# install.packages("pak")
pak::pak("1catherinem/CWS-Pathway-of-Effects")
```

**On Windows**

On Windows you may need to install RTools. If you try the above code but get a message to this effect download and install [RTools](https://cran.r-project.org/bin/windows/Rtools/) for your R version. You can find your R version by looking at the first line in the R Console when you start RStudio (if a govt user, likely R 4.4.x).

Close RStudio and restart.

Try installing again:

``` r
# install.packages("pak")
pak::pak("1catherinem/CWS-Pathway-of-Effects")
```
## Getting Started

Create an RStudio project and place the custom excel data files in this folder.

Then launch the Shiny UI with `poe_tool()`:

``` r
library(poe)
poe_tool()
```
Troubleshooting note: If poe_tool() is run and the error message "Template content not set during policy execution" appears, close RStudio, then open it and the project again and run the tool once more. A restart _should_ fix this error.

## Advanced setup: Run from R files

To run the tool from the repository, follow these steps:

1.	Download the whole repository from https://github.com/1catherinem/CWS-Pathway-of-Effects (or the most updated version) – Do this by clicking on the green “Code” button and clicking “Download ZIP.”
2.	Extract the ZIP file.
3.	Inside the Pathway-Of-Effects folder, import your four XSLX files into the R folder.
4.	Open RStudio. 
5.	File>New Project in RStudio, create a new project inside the main pathway-of-effects folder.
6.	To install and load all necessary packages, run: pak::pak("marleyaikens/CWS-Pathway-of-Effects"). 
7.	Open the R folder and all of the R files inside in RStudio.
8.	Run each of the R files completely (may need to run some of the files multiple times, see troubleshooting notes 1 and 2), running app.R last. Install packages as needed when prompted by RStudio.
9.	If all goes well, the app will launch! (fingers crossed) (see troubleshooting note 3)


### Troubleshooting the Advanced setup
Note 1: If an error is thrown that looks like: "Error in X() : could not find function "X()" Called from: poe_tool()", then run all of the scripts again (You can also ctrl+f and search for that function in each of the files, then run the one with the "missing" function.). Look to see if the "missing" function is in your "Environment" pane on the right. Once you see it, run app.R again.

Note 2: If utils.R throws errors, run the other R files first, then run utils.R. If utils.R still throws errors, run it again until it doesn't.

Note 3: If App.R is run but opens an RStudio window with no contents, click on "View in browser" near the top of the window. 


### Basic Workflow

1.  **Select a Valued Component** from the dropdown (e.g., "Marine Birds", "Wetlands")

2.  (Optional) **Choose a Sector** to pre-select activities associated with specific sectors.

3.  Further **Select Activities** relevant to your project

4.  **View the Pathway** showing how activities lead to stressors, effects, and outcomes

5.  **Apply Mitigations** to see how they alter pathway outcomes

    - Option to create and apply custom mitigations

6.  **Generate a Report** documenting your pathway

## Learning More

- To explore customizing the data, see [CUSTOM-DATA.md](CUSTOM-DATA.md)
- To learn more about the coding and design choices, see [CODE-DESIGN.md](CODE-DESIGN.md)
- To make a new release of this R package, follow instructions in [RELEASE.R](RELEASE.R)
- To learn more about R package development and workflows, see:
  - [R Packages](https://r-pkgs.org/) - Excellent guide, standard used by many people
  - [rOpenSci's developer Guide](https://devguide.ropensci.org/) - Good but detailed and meant for packages going to be submitted for Peer-Review
- How to setup and use the R-Universe - <https://docs.r-universe.dev/publish/set-up.html>

## License

MIT + file LICENSE
