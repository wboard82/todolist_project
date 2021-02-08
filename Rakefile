require 'rake/testtask'
require 'find'
require 'bundler/gem_tasks'

desc 'Say hello'
task :hello do
  puts "Hello there. This is the 'hello' task."
end

desc 'Run tests'
task :default => :test

Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']
end

desc 'List all files'
task :ls do
  Find.find('.') do |path|
    if FileTest.directory?(path)
      if path.include?('/.')
        Find.prune
      else
        next
      end
    else
      puts path
    end
  end
end
