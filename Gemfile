# frozen_string_literal: true

source 'https://rubygems.org'

gemspec

gem 'asciidoctor'
gem 'bump', require: false
gem 'bundler', '>= 1.15.0', '< 3.0'
gem 'memory_profiler', platform: :mri
# FIXME: This is a workaround for incompatibilities between Prism 0.25.0 and 0.26.0.
# To upgrade to Prism 0.26+, it is necessary to investigate the following build error
# and provide feedback to Prism:
# https://github.com/rubocop/rubocop/actions/runs/8748485587/job/24008584735?pr=12855
gem 'prism', '0.25.0'
gem 'rake', '~> 13.0'
gem 'rspec', '~> 3.7'
gem 'rubocop-performance', '~> 1.21.0'
#gem 'rubocop-checkstyle_formatter'
gem 'rubocop-rake', '~> 0.6.0'
gem 'rubocop-rspec', '~> 2.29.1'
# This is a workaround to prevent the following error in rubocop-rspec_rails 2.28.3:
# https://github.com/rubocop/rubocop/actions/runs/8656558784/job/23737409762
# Please remove this dependency when the issue is resolved.
gem 'rubocop-rspec_rails', '2.28.2'
# Workaround for cc-test-reporter with SimpleCov 0.18.
# Stop upgrading SimpleCov until the following issue will be resolved.
# https://github.com/codeclimate/test-reporter/issues/418
gem 'simplecov', '~> 0.10', '< 0.18'
gem 'stackprof', platform: :mri
gem 'test-queue'
gem 'yard', '~> 0.9'

group :test do
  gem 'webmock', require: false
end

local_ast = File.expand_path('../rubocop-ast', __dir__)
gem 'rubocop-ast', path: local_ast if Dir.exist? local_ast

local_gemfile = File.expand_path('Gemfile.local', __dir__)
eval_gemfile local_gemfile if File.exist?(local_gemfile)
