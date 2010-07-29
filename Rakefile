require 'rubygems'
require 'rake'
require 'rake/testtask'

APP_VERSION = "2.3.0"
APP_NAME    = 'Ruby on Rails.tmbundle'
APP_ROOT    = File.dirname(__FILE__)
RUBY_APP    = 'ruby'

require "choctop"

ChocTop::Configuration.new do |s|
  s.name = 'Ruby on Rails.tmbundle'
  
  s.add_root :position => [220, 180], :exclude => %w[appcast build .bundle .git]
  s.add_link 'http://github.com/drnic/ruby-on-rails-tmbundle', 'GitHub', :position => [440, 180]

  s.defaults :textmate

  s.base_url   = 'http://drnicwilliams.com/wp-content/uploads/tmbundles/'
  s.remote_dir = '/path/to/upload/folder'
  s.user       = 'anaptism'
end

desc "TMBundle Test Task"
task :default => [ :test ]
Rake::TestTask.new { |t|
  t.libs << "test"
  t.pattern = 'Support/test/*_test.rb'
  t.verbose = true
  t.warning = false
}
Dir['tasks/**/*.rake'].each { |file| load file }
