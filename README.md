# SpreeStripeSubscriptions

Spree extension to manage stripe subscriptions using Stripe Checkout Session.

## Installation

1. Add this extension to your Gemfile with this line:

    ```ruby
    gem 'spree_stripe_subscriptions'
    ```

2. Install the gem using Bundler

    ```ruby
    bundle install
    ```

3. Copy & run migrations

    ```ruby
    bundle exec rails g spree_stripe_subscriptions:install
    ```

4. Restart your server

  If your server was running, restart it so that it can find the assets properly.

## Configurations

### Customise Stripe Plans URL

To use customise URls, you can set the following configurations:

```ruby
# In initializers/spree_stripe_subscriptions.rb
SpreeStripeSubscriptions::Config.stripe_plans_path = 'pricing' # Default url is 'stripe_plans'
SpreeStripeSubscriptions::Config.stripe_webhooks_path = 'webhook' # Default url is 'stripe_webhooks'
```

## Testing

First bundle your dependencies, then run `rake`. `rake` will default to building the dummy app if it does not exist, then it will run specs. The dummy app can be regenerated by using `rake test_app`.

```shell
bundle update
bundle exec rake
```

When testing your applications integration with this extension you may use it's factories.
Simply add this require statement to your spec_helper:

```ruby
require 'spree_stripe_subscriptions/factories'
```

## Releasing

```shell
bundle exec gem bump -p -t
bundle exec gem release
```

For more options please see [gem-release REAMDE](https://github.com/svenfuchs/gem-release)

## Contributing

If you'd like to contribute, please take a look at the
[instructions](CONTRIBUTING.md) for installing dependencies and crafting a good
pull request.

Copyright (c) 2022 [name of extension creator], released under the New BSD License
