require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "tree_select"
    gem.summary = %Q{tree_select as a gem}
    gem.description = %Q{tree_select as a gem}
    gem.email = "szymon@jez.net.pl"
    gem.homepage = "http://jeznet@github.com/jeznet/tree_select"
    gem.authors = ["Stijn (stijnster) Mathysen","Rails 3 patch Szymon (jeznet) Jeż"]
    gem.add_dependency('acts_as_tree', '>= 1.2.3')
    gem.requirements << 'This source http://github.com/parasew/acts_as_tree.git of acts_as_tree works.'
    # gem.add_development_dependency "thoughtbot-shoulda"
    # gem is a Gem::Specification... see http://docs.rubygems.org/read/chapter/20 for additional settings
  end
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: sudo gem install jeweler"
end

require 'rake/testtask'
Rake::TestTask.new(:test) do |test|
  test.libs << 'lib' << 'test'
  test.pattern = 'test/**/*_test.rb'
  test.verbose = true
end

begin
  require 'rcov/rcovtask'
  Rcov::RcovTask.new do |test|
    test.libs << 'test'
    test.pattern = 'test/**/*_test.rb'
    test.verbose = true
  end
rescue LoadError
  task :rcov do
    abort "RCov is not available. In order to run rcov, you must: sudo gem install spicycode-rcov"
  end
end

task :test => :check_dependencies

task :default => :test

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  if File.exist?('VERSION')
    version = File.read('VERSION')
  else
    version = ""
  end

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "tree_select #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
