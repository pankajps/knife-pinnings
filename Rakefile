require 'bundler'
require 'rubygems'
require 'rspec/core/rake_task'
require 'rdoc/task'

Bundler::GemHelper.install_tasks

task :default => :spec

desc 'Run specs'
RSpec::Core::RakeTask.new(:spec) do |spec|
  spec.pattern = 'spec/**/*_spec.rb'
end

# rubocop:disable Lint/Eval
gem_spec = eval(File.read('knife-pinnings.gemspec'))
# rubocop:enable Lint/Eval

RDoc::Task.new do |rdoc|
  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "knife-push #{gem_spec.version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
