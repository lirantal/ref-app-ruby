# Reference Ruby application on Docker

## A sample Ruby on Rails application inside Docker

The following is a supportive `Dockerfile` and `docker-compose.yml` to run a Ruby on Rails application inside Docker.
It's useful for development and testing and we can use it to easily bring up a Ruby environment to work on that outside of our own host environment.

Start off with building the Docker image:

```sh
docker-compose build
```

Run the Ruby container image:

```sh
docker-compose run --rm --service-ports ruby_dev
```

Then inside the container's shell, initialize a new Ruby on Rails application project:

```sh
rails new myapp
cd myapp
bundle update
bundle install
```

Then run the server (listening on port 3000 per the `Dockerfile` declaration):

```sh
rails server -p $PORT -b 0.0.0.0
```

