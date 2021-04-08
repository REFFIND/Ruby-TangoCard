# Tangocard

Ruby Wrapper for Tango Card RaaS API.

Tango Card provides a RaaS API for developers (https://www.tangocard.com/docs/raas-api/). This gem provides commonsense Ruby
objects to wrap the JSON endpoints of the RaaS API.

## Getting Help

* Please report bugs on the [issue tracker](https://github.com/bonusly/tangocard/issues)

## Installation

Create an initializer, e.g. `config/initializers/tangocard.rb`:

```
Tangocard.configure do |c|
  c.name = "BonuslyXYZ"
  c.key = "Dnv9ehvff29"
  c.base_uri = "https://sandbox.tangocard.com"
end
```

There are three required configuration parameters:

 * `name` - The API account name you receive from Tango Card
 * `key` - The API account key you receive from Tango Card
 * `base_uri` - This defaults to the Tango Card sandbox.  For production, you must specify the base URI for the production RaaS API. Make sure not to include `/raas/v1` or any trailing slashes.

There are also optional configuration parameters:

 * `default_brands` - An array of strings for the brands you want to retrieve with `Tangocard::Brand.default`. The strings should match the unique brand `description` fields exactly.
 * `local_images` - An array of local image names/URIs that you want to display instead of the default Tango Card-provided `image_url`. `image_url` is sometimes blank, so this can be handy in those cases.
 * `sku_blacklist` - Reward SKUs that are blacklisted, ie. should never be returned as a purchasable reward.
 * `use_cache` - Use cache for Tangocard::Brand queries, defaults to `true`. The cache can be refreshed by calling `Tangocard.warm_cache`
 * `cache` - Which cache to use, defaults to `ActiveSupport::Cache::MemoryStore`. Using an out-of-process cache e.g. hosted memcache will improve performance and stability.
 * `logger` - i.e. `Rails.logger`

## Getting Started

This gem provides two tools:

1. A simple wrapper for the Tango Card RaaS API, consisting of two classes: `Tangocard::Raas` and `Tangocard::Response`.
2. Models for each of the Tango Card objects: `Tangocard::Account`, `Tangocard::Brand`, `Tangocard::Reward`, `Tangocard::Order` and `Tangocard::ExchangeRate`. These provide a greater level of abstraction and ease of use.

