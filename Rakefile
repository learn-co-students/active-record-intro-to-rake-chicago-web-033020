#Now, let's namespace both hello and hola under the greeting heading:
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

#We'll call this task migrate, because it is a convention to say
#we are "migrating" our database by applying SQL statements that alter that database.
namespace :db do
  desc 'migrate changes to your database'
  task :migrate => :environment do
    Student.create_table
  end

  task :environment do
    require_relative './config/environment'
  end
#We define a rake task that executes the code in this file.
#This task will also be namespaced under db
  desc 'seed the database with some dummy data'
  task :seed do
    require_relative './db/seeds.rb'
  end

end

#We'll define a task that starts up the Pry console.
#We'll make this task dependent on our environment task
#so that the Student class and the database connection load first.
desc 'drop into the Pry console'
task :console => :environment do
  Pry.start
end
