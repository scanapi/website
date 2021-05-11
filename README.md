![](https://github.com/scanapi/design/raw/main/images/github-hero-dark.png)
[![Netlify Status](https://api.netlify.com/api/v1/badges/54affc49-c5e1-472b-b8b9-174d3300ee8a/deploy-status)](https://app.netlify.com/sites/gracious-cray-a1ce6a/deploys)

# ScanAPI Website

Website for [ScanAPI](https://github.com/scanapi/scanapi) testing framework.

Available at: [scanapi.dev](https://scanapi.dev)

## Tech Stack
- [Jekyll](https://jekyllrb.com)
- Deploys by [Netlify](https://www.netlify.com)

## Development
### Install
#### Ruby
- It is necessary to have ruby to run jekyll, to perform the verification with the following code, run `ruby -v`, if you return the version of ruby, you have it installed on your machine, otherwise install following the steps in documentation [here](https://www.ruby-lang.org/en/downloads/)
    -  We will not go into details of the ruby installation step by step as it is not the focus!

### Jekyll
-  After installing ruby, [install](https://jekyllrb.com/docs/installation/) jekyll
    1. Run the command `gem install bundler jekyll`
    2. Check if the installation was successful by running the command `jekyll -v`
    3. To execute the project live, run the command `bundle exec jekyll serve`

### ⚠️ Troubleshooting

1. Error of the outdated version of ruby, this is due to the Jekyll running only in versions >= 2.5.0. To correct it, you need to install a newer ruby version. We encourage you to use [RVM](https://rvm.io) to manage your Ruby versions.

2. Absence of `gcc`, `make`, and `rubygems`. This is due to Jekyll having pre-requisites. To verify if they are installed:
    - Run the comands, `ruby -v`, `gem -v`, `gcc -v`, `g++ -v` and `make -v`
    - [RubyGems](https://rubygems.org/pages/download), [GCC](https://gcc.gnu.org/install/) and [Make](https://www.gnu.org/software/make/)

## Run

```bash
$ bundle exec jekyll serve
```
