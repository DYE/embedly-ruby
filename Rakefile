require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "embedly"
    gem.summary = %Q{Ruby Embedly client library}
    gem.description = %Q{Ruby Embedly client library}
    gem.email = "bob@embed.ly"
    gem.homepage = "http://github.com/embedly/embedly-ruby"
    gem.authors = ["Bob Corsaro"]
    gem.add_development_dependency "cucumber", ">= 0"
    gem.add_development_dependency "jeweler", ">= 0"
    gem.add_development_dependency "rspec", ">= 0"
  end
  Jeweler::GemcutterTasks.new

rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: gem install jeweler"
end

begin
  require 'cucumber/rake/task'
  Cucumber::Rake::Task.new(:features)
rescue LoadError
  task :features do
    abort "Cucumber is not installed"
  end
end

begin
  require 'yard'
  YARD::Rake::YardocTask.new do |t|
      t.files = FileList['lib/**/*.rb'].exclude('lib/jeweler/templates/**/*.rb')
  end
rescue LoadError
  task :yard do
    abort "Yard is not installed"
  end
end

task :features => :check_dependencies

task :default => :features

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "embedly #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
