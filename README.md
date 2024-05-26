# Constelleum Website

This website is hosted on github.io.

## Installation Requirements

1. Ruby
2. 'github-pages', group: :jekyll_plugins (`gem install bundler jekyll`)

## Setting up

1. Get the website repository: `git clone https://github.com/cardbattler/carbattler.github.io.git`
2. Install ruby dependencies: `bundle install`

## Running the Development Server

1. `bundle exec jekyll serve` -> site should now be available on `localhost:4000`

## Building files for Production Deploy

1. `bundle exec jekyll build` -> files are rendered to `_site` and can be transferred from there to their final home.
