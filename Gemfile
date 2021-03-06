# frozen_string_literal: true

source 'https://rubygems.org'

git_source(:github) { |repo_name| "https://github.com/#{repo_name}.git" }

branch = ENV.fetch('SOLIDUS_BRANCH', 'master')
gem 'solidus', github: 'solidusio/solidus', branch: branch

# Needed to help Bundler figure out how to resolve dependencies,
# otherwise it takes forever to resolve them
if branch == 'master' || Gem::Version.new(branch[1..-1]) >= Gem::Version.new('2.10.0')
  gem 'rails', '~> 6.0'
else
  gem 'rails', '~> 5.0'
end

case ENV['DB']
when 'postgresql'
  gem 'pg', '~> 0.21'
when 'mysql'
  gem 'mysql2', '~> 0.4.10'
else
  gem 'sqlite3'
end

group :test do
  gem 'rails-controller-testing'
end

gem 'solidus_extension_dev_tools', github: 'solidusio-contrib/solidus_extension_dev_tools'

gemspec
