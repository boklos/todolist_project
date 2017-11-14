require "bundler/gem_tasks"
require "rake/testtask"
require 'find'

desc 'Say hello'
task :hello do
  puts "Hello there. This is the 'hello' task."
end

desc 'Run tests'
task :default => :test

Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb'] #any file that ends with _test.rb
end

desc 'Display inventory of all files'
task :inventory do
  Find.find('.') do |name|
    next if name.include?('/.') # Excludes files and directories with . names
    puts name if File.file?(name) #File::file?(filename)
  end
  # ./Gemfile
  #./Gemfile.lock
  #./README.md
  #./Rakefile
  #./lib/todolist_project.rb
  #./test/todolist_project_test.rb
end