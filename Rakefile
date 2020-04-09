namespace :greeting do

  desc 'outputs hello to the terminal'
  task :hello do
    puts "hello from Rake!"
  end

  desc 'outputs hola to the terminal'
  task :hola do
    puts "hola de Rake!"
  end
end

desc 'set up environment'
task :environment do 
  require_relative './config/environment' 
end

namespace :db do
  desc 'migrates changes to the database'
  task :migrate => :environment do
    Student.create_table
  end

  desc 'seed some dummy data into the database'
  task :seed do
    require_relative './db/seeds.rb'
  end
end

desc 'Drop into a pry session'
task :console => :environment do
  Pry.start
end
