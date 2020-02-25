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

namespace :db do 
  task :environment do 
    require_relative './config/environment'
  end 
  
  desc 'migrate changes to your database'
  task :migrate => :environment do
    Student.create_table
  end
  
  desc 'seed the database with some dummy data'
  task :seed do 
    require_relative './db/seeds.rb'
  end 
  
end

#rake console does not work for me outside of the namespace for :db...when it's not in :db, it passes the tests, but does not bring up console in the terminal. When I put the code for the console inside of the :db namespace, the console runs in the terminal, BUT no longer passes the tests!
desc 'drop into the Pry console'
task :console => :environment do 
  Pry.start 
end 
