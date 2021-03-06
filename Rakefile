require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "flightcaster"
    gem.summary = %Q{Simple interaction with the flightcaster API}
    gem.description = %Q{Simple interaction with the flightcaster API. Look up
    flight predictions and information.}
    gem.email = "jarod.luebbert@gmail.com"
    gem.homepage = "http://github.com/jarodluebbert/flightcaster"
    gem.authors = ["Jarod Luebbert"]
    gem.add_development_dependency "thoughtbot-shoulda", ">= 2.10.2"
    gem.add_development_dependency "shoulda", ">= 2.10.2"
    gem.add_development_dependency "mhennemeyer-matchy", ">= 0.3.3"
    gem.add_development_dependency "fakeweb", ">= 1.2.8"
    gem.add_dependency "httparty", ">= 0.5.2"
    gem.add_dependency "hashie", ">= 0.1.8"
    # gem is a Gem::Specification... see http://www.rubygems.org/read/chapter/20 for additional settings
  end
  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: gem install jeweler"
end

require 'rake/testtask'
Rake::TestTask.new(:test) do |test|
  test.libs << 'lib' << 'test'
  test.pattern = 'test/**/test_*.rb'
  test.verbose = true
end

begin
  require 'rcov/rcovtask'
  Rcov::RcovTask.new do |test|
    test.libs << 'test'
    test.pattern = 'test/**/test_*.rb'
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
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "flightcaster #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
