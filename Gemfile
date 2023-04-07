# frozen_string_literal: true

source "https://rubygems.org"
gemspec

# Bailey3D: Fix for live reload not working
#           See: https://stackoverflow.com/questions/30682575/unable-to-load-the-eventmachine-c-extension-to-use-the-pure-ruby-reactor
gem 'eventmachine', '1.2.7', git: 'https://github.com/eventmachine/eventmachine.git', tag: 'v1.2.7'

group :jekyll_plugins do
    gem "jekyll-feed", "~> 0.6"
    gem "jekyll-sitemap"
    gem "jekyll-paginate"
    gem "jekyll-seo-tag"
    gem 'jekyll-redirect-from'
end

