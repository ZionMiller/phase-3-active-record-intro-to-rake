require "pry"

# logs hello to terminal
namespace :greeting do

  desc "outputs hello to the terminal"
  task :hello do
    puts "hello from Rake!"
  end

  desc "outputs hola to the terminal"
  task :hola do
    puts "hola de Rake!"
  end

end

# connects path to db for entries
namespace :db do
  
  task :environment do
    require_relative "./config/environment"
  end
  
  desc "migrate changes to your database"
  task migrate: :environment do
    Student.create_table
  end

end

# seeds placeholder data from other db pathway
namespace :db do

  desc "seed the databse with some dummy data"
  task seed: :environment do
    require_relative "./db/seeds"
  end

end

# opens a console session with pry, since relies on environment
# instead of Student, Student class and database connection load first
# not namespaced under db (way to group something) because its more general
desc 'drop into the Pry console'
task console: :environment do
  Pry.start
end
