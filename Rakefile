# frozen_string_literal: true

require 'dotenv'
require 'standalone_migrations'

Dotenv.load

ENV['SCHEMA'] = File.join(ActiveRecord::Tasks::DatabaseTasks.db_dir, 'schema.rb')
StandaloneMigrations::Tasks.load_tasks

# start pipeline
task :dev do
  ruby 'bin/pipeline.rb'
end

# debug pipeline
task :dev_debug do
  sh 'export SCHEDULE_DATE=2023-03-31 MODE=debug && ruby bin/pipeline.rb'
end
