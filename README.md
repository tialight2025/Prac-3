# Practical 3 — Exploratory Data Analysis

This repository is where you'll write up your answers for Practical 3
("Working with Data: Exploratory Data Analysis").

## Repository contents

```
.
├── README.md                  <- this file
└── practical3-answers.qmd     <- template: fill in your answers here
```

There's no `data/` folder this week. The dataset is bundled R
package `palmerpenguins`.

## 1. Get the repository onto your computer

Use this repository as a template for your own personal answers.

(i) Click "Use this template" then "Create a new repository" and follow prompts to create a personal copy of this repo.

(ii) Clone the repo to your local computer with RStudio: **File > New Project > Version Control > Git**

(iii) Follow the prompt and paste your **personal repo**'s URL.

## 2. Get the data

No files to download this week. The dataset (`penguins`) is bundled with the
`palmerpenguins` package.

## 3. Install the packages you'll need

Open `practical3-answers.qmd` in RStudio and try running the setup chunk at
the top. If any `library()` call fails with something like
`Error in library(palmerpenguins) : there is no package called 'palmerpenguins'`,
install the missing package(s) from the R console:

```r
install.packages(c("ggplot2", "tidyr", "dplyr", "naniar", "palmerpenguins", "GGally"))
```

You only need to do this once per machine. After installation `library()` will
work to load the package. A few tips:

- Install packages in the **Console**, not inside the `.qmd` file itself.
  If `install.packages()` calls end up inside a code chunk, they'll try to
  reinstall the package every time you render the document, which is slow
  and unnecessary.
- `GGally` pulls in a few dependencies of its own, so its install may take a
  little longer than the others.
- Package documentation and vignettes worth skimming before you start:
  [ggplot2](https://ggplot2.tidyverse.org/articles/ggplot2.html),
  [dplyr](https://dplyr.tidyverse.org/articles/dplyr.html),
  [naniar](https://naniar.njtierney.com/articles/naniar.html),
  [GGally](https://ggobi.github.io/ggally/index.html) (see the "Articles" tab).

## 4. Answer the practical

Work through `practical3-answers.qmd` in order. Write code in the empty
chunks and add your written answers underneath each question heading.

Render regularly (the "Render" button in RStudio, or
`quarto::quarto_render("practical3-answers.qmd")`) to check your document
still runs cleanly from top to bottom. Rendering in a fresh R session
(**Session > Restart R**, then Render) is the best way to check your script
is fully reproducible.

## 5. Commit and push your work

Commit early and often as you go, rather than in one big commit at the end —
it makes it much easier to see your progress and to recover earlier work if
something breaks.

You can use the RStudio console or in terminal.

If you're unsure what a Git error message means, the
[Happy Git](https://happygitwithr.com/) book (or pasting the exact error into
a search engine) is usually the fastest way to unblock yourself — most Git
errors are common and well documented.

## Troubleshooting checklist

- **"Package not found"** → install it from the Console (see step 3).
- **`penguins` object not found** → make sure you've run
  `library(palmerpenguins)` in your session to load it.
- **Document won't render but code runs fine chunk-by-chunk** → try
  Session > Restart R, then Render again; this catches missing `library()`
  calls or objects created out of order.
- **Plot looks empty or drops points unexpectedly** → check for a "Removed
  rows containing missing values" warning under the plot; `ggplot2` silently
  drops `NA`s for the mapped variables, which is worth mentioning in your
  answer where relevant (see Question 9).
