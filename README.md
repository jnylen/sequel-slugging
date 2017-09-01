# Sequel::Slugging

Slugging is a plugin for Sequel that creates slugs from names or similar with an built-in uuid fix for duplicates.

This gem is quite similar to `friendly_id`

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'sequel_slugging', github: 'jnylen/sequel_slugging'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install sequel-slugging

## Usage

Please look in the spec folder for examples.

Basically it's just `plugin :slugging, source: :name` where name is the column you want to grab the slug from.

## History

You can keep a slug in history so you can still fetch it when it has changed.

First you need to create a table using this:
```ruby
create_table :slug_history do
  primary_key :id
  text :slug, null: false
  integer :sluggable_id, null: false
  text :sluggable_type, null: false
  timestamptz :created_at, null: false
end
```

Then add `history: :slug_history` to your plugin line for slugging.

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake test` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/jnylen/sequel_slugging. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](contributor-covenant.org) code of conduct.


## License

The gem is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).

## Authors

Creator: [Chris Hanks](https://github.com/chanks/sequel-slugging)
Maintainer: [Joakim Nylén](https://github.com/jnylen/sequel_slugging)
