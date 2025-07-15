# Website Template

Here is a brief walkthrough of things to update in order to have your website appear. 

# The Template Repository

When creating a project from this template, be sure to check "Include all branches". This will copy in the additional branches that are necessary to publish your site more easily.

There should be 3 different branches
1. main (default)
2. gh-pages
3. github-action

Remember that the name of the repository will be your pages URL
e.g. https://dharaden.github.io/site-template

## After Creating your own repository

### Step 1: Allow GitHub Action to render website
- Navigate to the current repo and select settings
- Settings > Actions > General
- Scroll down to "Workflow permissions"
-  Make sure "Read and write permissions" is selected (this gives the github-actions[bot] permission to push)

### Step 2: Check Pages
This should already be set up and your site will likely have already been published, but this is good to double check. 

- Settings > Pages 
    - Source should "Deploy from a branch"
    - The branch selected is "gh-pages" and the "/(root)" folder

This will use GitHub Actions to basically create an R environment and render all of your code to create the appropriate files for publishing the website.  

### Step 3: Open in R-Studio
Open the project in R-Studio. You will see that `renv` will already try to work and you will get the message: 
- None of the packages recorded in the lockfile are currently installed.
- Use `renv::restore()` to restore the project library."
The next step will be to run `renv::restore()` in your R console. This will check to see what libraries are in this repository that you do not currently have on your machine and will ask you to install them. 

You will only have to restore the environment once when opening it on a new computer. Review the documents for `renv` for more info: https://rstudio.github.io/renv/articles/renv.html

# Using the template

There are a lot of different ways to use this repository with countless tempaltes. Here are just a few things to help guide and some additional resources. 

## The R Environment
As stated above, the GitHub Actions creates an R environment to run the code. Therefore, we need to make sure that all libraries are installed into this since it is a new instance each time. 

We use the package `renv` to help out with keeping everything synced between the R-Studio that you work on and the R code that gets run through GitHub. 

Here is the website for `renv`: https://rstudio.github.io/renv/articles/renv.html

### Installing a new package 
Whenever you need to install a new package to use on your site, be sure to take a snapshot of the current installed packages using `renv::snapshot()`


## Website Structure
Each page on your website can be represented by different QMD files. 

The orgainzation of the file structure for your website will be found in the `_quarto.yml` file. This page will open in a text editor and will allow you to edit the title, logo, structure and all properties of the wesbite.

To re-organize the order of the website, you will navigate to `contents:` in the `_quarto.yml` file. Here you will be able to edit the name of the link and then which QMD file to direct it to. These use relative file paths with the parent folder being where the README.md file is. 

### Home Page
This will be the `index` file. Update to include any information that you may need on the landing page of your site. 

### Other pages and sub-pages
The current setup is an example of various pieces of content from tables to sub-pages. Please edit to fit your needs. 

# Usefule Info
I always found the best way to update things is through copying what other smart people have been doing. One of those people is Mine Çetinkaya-Rundel. She is a wizard when it comes to R and anything data. She has all of her teaching websites here (https://mine-cr.com/teaching/) that has links to all the github repositories. The current template is an update to what she had for one of her courses. This is one of my favorites right now (https://github.com/sta210-s22/website). 

I have also pulled info from OpenScapes (https://openscapes.github.io/quarto-website-tutorial/). This can be a good introduction just to get familiar with the flow of things. 