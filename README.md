Docker for Rails, Pragmatic Book
July 9, 2019

Starting chp8, Rspec 
pg 97.

#urls
http://localhost:3000/welcome
http://localhost:3000/users
http://localhost:3000/pages/home

#Rails
1. docker run -i -t --rm -v ${PWD}:/usr/src/app ruby:2.6 bash
   gem install rails
   rails new myapp --skip-test --skip-bundle
   exit
2. docker build -t docker_rails .

3. Gemfile, pg75 
    gem 'pg', '~> 1.0'
    
4. docker-compose run --rm database psql -U postgres -h database
   docker-compose rm -f database
   docker-compose up -d database
   docker-compose up -d --force-recreate web
   docker-compose exec web bin/rails db:create db:migrate
   docker-compose [rm, stop] database
   
5. docker volume [ls rm]
6. docker-compose build web
7. docker system prune    --pg 57, free up resources
8. docker-compose exec web rails g controller welcome index
9. docker-compose exec web rails g scaffold User first_name:string last_name:string
10. docker-compose exec web rails db:migrate    -- pg80
11. rm tmp/pids/server.pid
12. docker-compose run web bin/rails webpacker:install
    docker-compose run web bin/rails webpacker:install:react
13. docker-compose up -d webpack_dev_server
14. docker-compose exec web bin/rails g controller pages home
15. docker-compose exec web rails generate rspec:install
16. docker-compose exec web rails spec  --pg 97

