# jekyll-theme-eclipsefdn

[![Build Status](https://travis-ci.org/eclipsefdn/jekyll-theme-eclipsefdn.svg?branch=master)](https://travis-ci.org/eclipsefdn/jekyll-theme-eclipsefdn)

This theme is currently experimental, but intended to provide the branding for Eclipse projects using GitHub pages for their documentation.
This Jekyll theme is intended to copy the theme of the main https://www.eclipse.org website so the projects use branding that is consistent with the main website.


![Screenshot](https://raw.githubusercontent.com/eclipsefdn/jekyll-theme-eclipsefdn/master/screenshot.png)

# Using the theme on your GitHub pages site

Eclipse projects typically publish their documentation using the GitHub pages functionality of the source code repository on GitHub. 
This involves pushing the documentation materials to the `gh-pages` branch in the repository. Once content has been pushed to this branch
it is publish statically at `https://eclipse.github.io/<projectname>`. Without a theme, the site will be published using a default
theme.

To use this theme in GitHub pages, simply specify:

`remote_theme: eclipsefdn/jekyll-theme-eclipsefdn` in `_config.yml` at the root of the `gh-pages` branch.
NOTE: this theme is currently being reviewed, and will move to a GitHub repository owned by the Eclipse Foundation.

Once the project has been set to use the theme, the project team should review each page on the site to ensure it renders correctly.
Any problems with the theme should be raised as an issue on this project, and pull requests are most welcome.

If you are publishing html files directly from `gh-pages`, please note that these are likely to require some additional work to ensure
the correct CSS and Javascipt is pulled in.

# Running the site locally

Follow these steps to run and check your project's site locally on your machine. Further instructions for Jekyll and GitHub pages can be
found here:

Pre-requisites:

* Ruby 2.1.0 or greater (check with `ruby --version`)

Instructions:

* (1 time only) Ensure you have a Gemfile in the root of your project with the following content:

````
source 'https://rubygems.org'
gem 'github-pages', group: :jekyll_plugins
gem 'jekyll-theme-eclipsefdn'
````

* (1 time only) Install the `bundler` gem: `gem install bundler`

* Install Jekyll and other dependencies: `bundle install`

* Switch the theme in `_config.yml`. Change this
````
remote_theme: eclipsefdn/jekyll-theme-eclipsefdn
````

to

````
theme: jekyll-theme-eclipsefdn
````

This will make sure the locally installed Gem will be used to render the site.

* Run the Jekyll site locally: `bundle exec jekyll serve`

# Building the theme (only necessary if you wish to make changes)

To build the theme itself, clone this repository (or your own fork of it), and do the following:

Pre-requisites:

* Ruby 2.1.0 or greater (check with `ruby --version`)

* Install the `bundler` gem: `gem install bundler`

* Install the dependencies: `bundle install`

* Build the Gem: `gem build jekyll-theme-eclipsefdn.gemspec`

Pushing the Gem to RubyGems

(please update the version number in `jekyll-theme-eclipsefdn.gemspec`)
* `gem push jekyll-theme-eclipsefdn-*.gem`

