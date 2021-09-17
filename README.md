# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

```
bundle lock --add-platform x86_64-linux Gemfile
bundle config --local build.mysql2 "--with-ldflags=-L/usr/local/opt/openssl@1.1/lib --with-cppflags=-I/usr/local/opt/openssl@1.1/include"
bundle install
bundle cache --all
bundle package --all-platforms
```

* Configuration

```
bin/docker --help
bin/docker setup
```

* Setup env

```
bin/redis start --publish
bin/db start --publish
 ```

* Database creation

```
bundle exec rake db:create
```

* Database initialization

```
bundle exec rake db:setup
```

* App Skeleton

```
bundle exec rails generate scaffold post name:string    
bundle exec rake db:migrate
```

* Test app

```
bundle exec rails server
```


```ruby
curl --location --request POST 'http://127.0.0.1:3000/posts' \
--header 'Content-Type: application/json' \
--header 'Accept: application/json' \
--data-raw '{
    "post": {
        "name": "Case of the Missing Green Journals",
    }
}'
```

```ruby
curl -X GET \
  -H "Accept: application/json" \
  -H "Content-type: application/json" \
  http://127.0.0.1:3000/posts | jq
```

* How to run the test suite

```
DB_HOST=127.0.0.1 \
DB_PORT=3335 \
bundle exec rake test
```

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
