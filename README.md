Docker for Rails, Pragmatic Book
July 5, 2019

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
   
5. docker volume [ls rm]