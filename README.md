# Hello, this is the project repo, the site's files are in ***docs*** folder and generated with Hugo command from the ***hugo*** folder

> In this document:
> * ```docs``` is a generated folder
> * ```hugo``` is a folder containing all the required files to maintain and update your site

## Hugo and Gihub Pages, to set from scratch

  * [Install Hugo](https://gohugo.io/getting-started/installing):
    * Ubuntu:

      ```bash
      sudo apt-get install hugo
      ```
  * Create a new site with the [Quickstart tutorial](https://gohugo.io/getting-started/quick-start/):
    * Create a new site directory where you want:

      ```bash
      hugo new site [NAME_OF_YOUR_SITE]
      ```

    * Git init:

      ```bash
      cd [YOUR_SITE_DIRECTORY]
      git init
      ```

    * Then choose a [theme](https://themes.gohugo.io)
    * Download the chosen theme (*for example [hugo-future-imperfect](https://github.com/jpescador/hugo-future-imperfect)*) as a submodule of your repo:

      ```bash
      git submodule add https://github.com/jpescador/hugo-future-imperfect themes/hugo-resume
      ```

    * Edit your config.toml configuration file to apply theme or just copy the ```config.toml``` of the theme and replace your own default ```config.toml```:

      ```bash
      echo 'theme = "hugo-future-imperfect"' >> config.toml
      ```
    * Go on the ***Settings*** of your GitHub online repo and in the ***GitHub Pages*** section choose ```master branch /docs folder``` as ***Source***, don't choose theme and copy the adress of the generated site.
    * In the ```config.toml```
    * Go to, for example, to ```hugo/content/blog``` directory and add a MarkDown file in it
    * If you want to check your changes, go to the root of ```hugo```:

      ```bash
      hugo server -D
      ```

    * If it's correct,git add, commit and push your changes or do a pull request
    * Then see ***How to update section***

## How to update

* In ***hugo*** folder, to generate site's files (*this will replace the original docs folder to apply do the changes and generate new html pages*):

  ```bash
  hugo -d ../docs
  ```

* Then you have to add, commit and push and your site will soon be updated (*few seconds/minutes for GitHub to apply the changes*)

## Warnings

* This is pretty simple but there is no continuous integration
* Need maybe a *web master/editor* to update and/or maintain the project's site
* Choose a theme with its advantages and disadvantages and deal with it, changes could take a lot of time

## Jekyll VS hugo

|                   | **HUGO** | *Hugo review* | **JEKYLL** | *Jekyll review* |
|:------------------|:---------|:-------------:|:-----------|:---------------:|
| ***Installation: base*** | Very simple (*one line on Linux*), No need to know Go | <img src="good.png" width="70%"> | Need to install Ruby to install Bundle to install Jekyll (*if you follow the Github Pages tutorial*). If errors, becomes very boring | <img src="bad.png" width="70%"> |
| ***Installation: theme*** | Lot of available themes, get one with good documentation and deal with its advantages and disadvantages because changes could cost a lot | <img src="good.png" width="70%"> | Lot of available themes, get one with good documentation and deal with its advantages and disadvantages because changes could cost a lot | <img src="good.png" width="70%"> |
| ***Checking***    | Possible local check on localhost, one line in terminal | <img src="good.png" width="70%"> | Possible local check on localhost, one line in terminal | <img src="good.png" width="70%"> |
| ***Integration (with GitHub Pages)*** | Update of a directory with content then need to generate a site directory (*when pushed to GitHub, site is updated automatically*) | <img src="good.png" width="70%"> <img src="bad.png" width="70%"> | Continuous integration | <img src="good.png" width="70%"> |
| ***Conclusion*** | Simple, Markdown, 1 command line to update | <img src="good.png" width="70%"> | Supposedly easy and pretty straightforward **if and only if** there is no installation or maintenance problem | <img src="bad.png" width="70%"> |
