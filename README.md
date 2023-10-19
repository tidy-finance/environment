# Tidy Finance Environment

This repository helps you to set up a development environment where you can work with both R and Python using the RStudio IDE. 

1. Install [R](https://cran.r-project.org/bin/windows/base/) and [RStudio](https://posit.co/download/rstudio-desktop/)
1. [Download or clone](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) the [Tidy Finance Environment](https://github.com/tidy-finance/environment) repository
1. Open `environment.Rproj` in the environment folder that you just downloaded
1. Install the R package `reticulate` (an interface to Python): `install.packages("reticulate")`
1. Install Python via `reticulate`: `reticulate::install_python(version="3.10.11", force = TRUE)`
1. Install the R package `renv` (an environment manager): `install.packages("renv")`
1. Tell `renv` to use Python: `renv::use_python("PATH")`
  a. `"PATH"` on Mac: `"~/.pyenv/versions/3.10.11/bin/python"`
  b. `"PATH"` on Windows: `"C:/Users/<User>/AppData/Local/r-reticulate/r-reticulate/pyenv/pyenv-win/versions/3.10.11/python.exe"` where `<User>` is your user name
1. Tell `renv` to install all required packages: `renv::restore()`

We decided to use Python version 3.10.11, after many trial and errors to set-up the environment that we used to write [Tidy Finance with Python](https://www.tidy-finance.org/python/) and maintain [Tidy Finance with R](https://www.tidy-finance.org/r/) on both Windows and Mac.

## Set Environment Variables

We use environment variables to secretly store our WRDS login credentials. 

- `.Renviron` is used by RStudio for all R code
- `.env` is used by Rstudio when it runs Python code via `reticulate`

Do not forget to add these two files to your `.gitignore` file if you plan to share your work publicly!

## Test code

Run this in the R console of your RStudio to check whether R code works:

```
library(tidyverse)

mtcars |> 
  filter()

```

Run this in the R console of your RStudio to check whether R code works:

```
library(tidyverse)

mtcars |> 
  filter(mpg > 20)

```

Run this in the R console of your RStudio to check whether Python code works:

```
reticulate::repl_python()

import numpy as np
import pandas as pd

pd.Series([1, 3, 5, np.nan, 6, 8])
```

## Open Issues

- Add instructions for VS Code
- ...
