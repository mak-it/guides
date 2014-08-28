# Ruby on Rails Guide

## Gems

* [HAML](https://github.com/haml/haml) for templates
* [Bootstrap](https://github.com/twbs/bootstrap-sass) for scaffold application styles
* [Email Validator](https://github.com/balexand/email_validator) for email
  validation
* [Postgres](https://github.com/ged/ruby-pg) or
  [MySQL2](https://github.com/brianmario/mysql2) for access to the database
* [Simple Form](https://github.com/plataformatec/simple_form) for form markup
  and style

For background jobs:

* [Resque](https://github.com/resque/resque) and
  [Resque Status](https://github.com/quirkey/resque-status) for background processing
* [Resque Scheduler](https://github.com/resque/resque-scheduler) for scheduling
  background jobs

For development:

* [Dotenv](https://github.com/bkeepers/dotenv) for loading environment variables
* [Pry Rails](https://github.com/rweng/pry-rails) for interactively exploring
  objects
* [Pry ByeBug](https://github.com/deivid-rodriguez/pry-byebug) for interactively
  debugging behavior
* [Spring](https://github.com/rails/spring) for fast Rails actions via
  pre-loading

For testing:

* [Capybara](https://github.com/jnicklas/capybara) and
  [Poltergeist](https://github.com/teampoltergeist/poltergeist) for
  integration testing
* [Factory Girl](https://github.com/thoughtbot/factory_girl) for test data
* [RSpec](https://github.com/rspec/rspec) for unit testing
* [Timecop](https://github.com/jtrupiano/timecop-console) for testing time

For production:

* [Airbrake](https://github.com/airbrake/airbrake) for exception notification
* [Unicorn](https://github.com/defunkt/unicorn) or
  [Puma](https://github.com/puma/puma) to serve HTTP requests
* [Rack Timeout](https://github.com/kch/rack-timeout) to abort requests that are
  taking too long
* [New Relic RPM](https://github.com/newrelic/rpm) for monitoring performance

## db/database.yml

PostgreSQL:

```yaml
_default: &default
  adapter: postgresql
  encoding: unicode
  pool: 5

development:
  <<: *default
  database: myapp_dev

test:
  <<: *default
  min_messages: WARNING
  database: myapp_test

production:
  <<: *default
  url: <%= ENV['DATABASE_URL'] %>
```

MySQL:

```yaml
default: &default
  adapter: mysql2
  encoding: utf8
  pool: 5
  username: root
  password:

development:
  <<: *default
  database: myapp_dev

test:
  <<: *default
  database: myapp_test

production:
  <<: *default
  url: <%= ENV['DATABASE_URL'] %>
```
