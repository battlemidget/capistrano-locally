# Capistrano::Locally

This gem is a Capistrano plugin to simplify "localhost" deployment.

Capistrano can deploy the source to any hosts including localhost via SSH (`SSHKit::Backend::Netssh`).
But when limiting to some simple case that deployment to localhost, SSH isn't sometimes necessary.

A `capistrano-locally` deploys without SSH only when a target host named "localhost"

So, you don't need to write SSH user and configs on `server 'localhost'`.

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'capistrano-locally'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install capistrano-locally

## Usage

Require in `Capfile`:

    require 'capistrano/locally'


### Example

`config/deploy/staging_and_local.rb`

    # typically server config is:
    server 'my.remotehost.com', roles: w%{app web}, user: 'deploy', key: '/path/to/key.pem'
    # localhost config is:
    server 'localhost', roles: w%{app web} # no need to set SSH configs.


## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake spec` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/[USERNAME]/capistrano-locally.

