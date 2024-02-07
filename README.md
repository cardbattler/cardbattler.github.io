# Constelleum Website

This website is built using jekyll 4.2. It should be possible to host on github.io, but it would require using the github gem, and checking the node_modules directory into github, which I currently have not done.

## Installation Requirements

1. Ruby
2. Jekyll 4.3.3 (`gem install bundler jekyll`)

## Setting up

1. Get the website repository: `git clone https://github.com/cardbattler/website.git`
2. Install ruby dependencies: `bundle install`

## Running the Development Server

1. `bundle exec jekyll serve` -> site should now be available on `localhost:4000`

## Building files for Production Deploy

1. `bundle exec jekyll build` -> files are rendered to `_site` and can be transferred from there to their final home.
