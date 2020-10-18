![](https://github.com/scanapi/design/raw/master/images/github-hero-dark.png)
[![Netlify Status](https://api.netlify.com/api/v1/badges/54affc49-c5e1-472b-b8b9-174d3300ee8a/deploy-status)](https://app.netlify.com/sites/gracious-cray-a1ce6a/deploys)

# ScanAPI Website

Website for [ScanAPI](https://github.com/scanapi/scanapi) testing framework.

Available at: [scanapi.dev](https://scanapi.dev)

## Tech Stack
- [Jekyll](https://jekyllrb.com)
- Deploys by [Netlify](https://www.netlify.com)

## Introduction
### Ruby installation
- It is necessary to have ruby to run jekyll, to perform the verification with the following code, run `ruby -v`, if you return the version of ruby, you have it installed on your machine, otherwise install following the steps in documentation [here](https://www.ruby-lang.org/pt/downloads/)
    -  We will not go into details of the ruby installation step by step as it is not the focus!

### Jekyll installation
- After installing ruby, install jekyll
    1. run the command `gem install bundler jekyll`
    2. Check if the installation was successful by running the command `jekyll -v`
    3. To execute the project live, run the command `bundle exec jekyll serve`

>### ⚠️ Problems that may occur
>1. Error of the outdated version of ruby, this is due to the jekyll running only in versions >= 2.5.0, to correct just use update the ruby version.
>2. absence of gcc, make, and rubygems this is due to jekyll having pre-requisites, check if they are installed:
    > - Run the comands, `ruby -v`, `gem -v`, `gcc -v`, `g++ -v` and `make -v`
