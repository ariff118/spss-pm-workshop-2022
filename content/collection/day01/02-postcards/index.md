---
date: "2022-06-25"
excerpt: In this block, we'll use the postcards package to make a single 'about' home
  page with only R Markdown.
subtitle: Model 1b - 1 Moderator with Categorical Moderator
title: Module 2
weight: 2
---

## Introduction  

- Example Variables: 1 predictor *X*, 1 moderator *W*, 1 outcome *Y*  

- *Preliminary Notes*  
  - Model 1b assumes that:  
    - The primary IV (variablle *X*) is continuous  
    - The moderator is categorical with multiple categories  

```
IV: Commitment  
MoDV: Bank (Size - Small, Medium, Large)  
DV: OP
```

> The impact of Commitment on Organizational Performance is moderated by the size of the Bank

## How to run in SPSS Process Macro?  

1. Insert model framework image here.  

2. Analyze > Regression > PROCESS v4.0 by Andrew fF. Hayes  
    Insert image here...  

3. Insert variables (*Y*, *X*, and *W*) and choose `Model 1`  
    Insert image here...  

4. Click Options button:  
    - check on `Generate code for visualizing interactions`  
    - Mean center - choose `Only continuous variables that define product`.  
    - click `Continue`

5. Click `Multicategorical` button:  
    - Under Variable W  
        - check box  
        - Coding system: `Indicator` (this will create a dummy coding for the moderator variable)
    - click `Continue`
    insert image here ...  

5. click `OK` to run analysis  

## Reading the output  

**Insert First Output Image Here**  

● Description of Model along with the different variables where *Y* is Dependent Variable, *X* is Independent Variable, and *W* is the Moderating Variable.  

● Bank is Categorical with Small, Medium, and Large Sized Banks.  

● Coding of categorical *W* variable for analysis:  

```
To Learn About Dummy Coding

    | Bank   | W1  | W2  |  
    |:------:|:---:|:---:|  
    | 1.000  | .000| .000|  
    | 2.000  |1.000| .000|  
    | 3.000  | .000|1.000|  
    
  W1 - Medium vs Small (Small is the Reference Category)  
  W2 - Large vs Small  
```

**Insert Second Image Output Here**  

:sparkles: Model Summary, provides summary of the model with $R$, $R^2$, $F$ statistic, and $p$ value for the overall model. Next, is the coefficients, with impact of *Commitment*, *Bank Size*, and the interaction effects to assess if there is moderation or not.  

:sparkles: Differences in *OP* between Medium and Small banks is insignificant (W1, *p* > 0.05). Medium sized banks have a higher *OP* in comparison to small sized banks.  

:sparkles: Differences in *OP* between Large and Small banks is significant (W2, $p$ < 0.05). Large sized banks has a lower *OP* in comparison to small sized banks.  

```
Can verify that the effect whether higher or lower in *OP* through the mean comparison. This can be done easily using SPSS:  
Go to Analyze > Compare Means > Means  
Dependent: *OP*  
Independent: *Bank*  
Click `OK`  
```

:sparkles: In this example, one interaction effect (Int_1) is significant. Impact of Commitment on Performance in Medium Sized Banks is considerably different (lower) from Small Sized Banks.  

:sparkles: However, impact of Commitment on Performance in Large Sized Banks is not significantly different from Small Sized Banks.  

:sparkles: Test of unconditional interaction. This shows the change in $R^2$ due to interaction _(x*w)_, this is also significant.  

:sparkles: Next, the conditional effects show that for Small and Large Sized Banks, the effects of Commitment on Organzational Performance is significant.  

### Data Visualization  

There are two ways to draw the interaction path in order to give you a clearer visulization on the effects of moderator on the relationship between the predictor and the outcome variable.  

1. Using the SPSS syntax  
    ✓ copy the script from the process macro output.  
    ✓ in SPSS, open a new syntax file  
    ✓ paste the script into your syntax file  
    ✓ click `Run` button to create your interaction graph  
    ...insert image here.  

2. Using the StatsTool package created by James Gaskin  
    ✓ link to download the STatTools Package ->  

**_Interpretation_**  
> 1. The study assessed the moderating role of Bank Size on the relationship between Commitment and Organizational Performance (OP). Test of unconditional interaction shows the change in $R^2$ due to interaction (x*w) is significant. The result revealed that although Medium Sized Banks have a higher OP in comparison to Small Size Banks. Differences in OP between Medium and Small bank were insignificant (W1, $p$ > 0.05)   

> 2. Furthermore, large sized banks have a lower *OP* in comparison to small size banks. Differences in *OP* between Large and Small banks were significant (W2, *p* < 0.05). In this example, one interaction effect (Int_1) is significant, such that, impact of Commitment on Performance in Medium sized banks is considerably different (lower) from Small sized banks. However, impact of Commitment on Performance in Large sized banks is not significantly different from Small sized banks.  

## Pre-requisites

First, make sure you have the latest version of the postcards package installed from CRAN:

```
install.packages("postcards")
```

Restart your R session. If you use RStudio, use the menu item *Session > Restart R* or the associated keyboard shortcut:

+ <kbd>Ctrl + Shift + F10</kbd> (Windows and Linux) or
+ <kbd>Command + Shift + F10<kbd> (Mac OS).

```
packageVersion("postcards")
[1] ‘0.2.0’
```

## Create GitHub repo

Online.

## Clone GitHub repo

```
usethis::create_from_github("https://github.com/apreshill/global-postcard.git")
```

:sparkles: Commit & Push! :sparkles:

You should be committing these files:

+ `*.Rproj`

+ `.gitignore`

## Create a postcard {#templates}

Inside your current postcards project, use the R console:

```
library(postcards)
```

Then you could run (wait- don't do this yet!):

```
create_postcard()
```

But you could also pick one of four templates:

1. `"jolla"` (<https://seankross.com/postcards-templates/jolla/>) [the default]

1. `"jolla-blue"` (<https://seankross.com/postcards-templates/jolla-blue/>)

1. `"trestles"` (<https://seankross.com/postcards-templates/trestles/>)

1. `"onofre"` (<https://seankross.com/postcards-templates/onofre/>)

```
create_postcard(template = "jolla") #default
create_postcard(template = "jolla-blue")
create_postcard(template = "trestles")
create_postcard(template = "onofre")
```

<aside>
Want to know more? Under the hood, these are R Markdown templates, which you can include in a package.
</aside>

## Anatomy of a postcard

YAML, body, name is index- this is special

:sparkles: Commit & Push! :sparkles:

You should be committing these files:

+ `index.Rmd`

+ `*.jpg`

But! There is no `.html` file (yet...)


## Knit the postcard

Knit button or

```
rmarkdown::render("index.Rmd")
```

What is new in your Git pane?

:sparkles: Commit & Push! :sparkles:

You should be committing this files:

+ `index.html`

(You may get a warning in RStudio IDE that this file is too big- go right ahead)

## Publish a postcard

Easy:

+ Push, publish to GitHub pages
https://docs.github.com/en/github/working-with-github-pages/creating-a-github-pages-site#creating-your-site

Medium:

```
> use_github_pages(branch = "main", path = "/")
✓ Setting active project to '/Users/alison/rscratch/global-postcard'
✓ Activating GitHub Pages for 'apreshill/global-postcard'
✓ GitHub Pages is publishing from:
● URL: 'https://apreshill.github.io/global-postcard/'
● Branch: 'main'
● Path: '/'
```

## Share your postcard!

Add it to your repository details

