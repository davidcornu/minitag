[![Gem Version](https://badge.fury.io/rb/minitag.svg)](https://badge.fury.io/rb/minitag)

# Minitag

[![Build Status](https://travis-ci.org/bernardoamc/minitag.svg?branch=master)](https://travis-ci.org/bernardoamc/minitag)

A simple gem that allow developers to tag their minitest tests and run tests
based on these tags.

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'minitag'
```

Or install it yourself as:

```
$ gem install minitag
```

## Usage

### Setup

Require `minitag` in our `test_helper.rb`:

`require 'minitag'`

### Adding tags

We can tag specific tests with one or more tags.


```rb
class MyTest < Minitest::Test
  tag 'my_tag', 'another_tag'
  test '#hello minitag' do
    # ...
  end
end
```

### Running tests

We can now run our test suite with specific tags:

`$ bundle exec rake test --tag 'my_tag'`

### Extra

Tags can be:
  1. `inclusive`
  2. `exclusive` with the `~` prefix:

### Examples
```rb
# Only run tests that are tagged with 'unit'
$ bundle exec rake test --tag 'unit'

# Only run tests that are NOT tagged with 'unit'
$ bundle exec rake test --tag '~unit'

# Only run tests that are tagged with 'unit' and are NOT 'parallel'
$ bundle exec rake test --tag 'unit' --tag '~parallel'
```

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake test` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/bernardoamc/minitag. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.

## License

The gem is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).

## Code of Conduct

Everyone interacting in the Minitag project’s codebases, issue trackers, chat rooms and mailing lists is expected to follow the [code of conduct](https://github.com/bernardoamc/minitag/blob/master/CODE_OF_CONDUCT.md).
