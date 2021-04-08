Tangocard

Ruby Wrapper for Tango Card RaaS API.

Tango Card provides a RaaS API for developers (https://www.tangocard.com/docs/raas-api/). This SDK provides commonsense Ruby objects to wrap the JSON endpoints of the RaaS API.

Installation

Create an initializer, e.g. config/initializers/tangocard.rb:

Tangocard.configure do |c|
  c.name = "BonuslyXYZ"
  c.key = "Dnv9ehvff29"
  c.base_uri = "https://sandbox.tangocard.com"
end
There are three required configuration parameters:

name - The API account name you receive from Tango Card
key - The API account key you receive from Tango Card
base_uri - This defaults to the Tango Card sandbox. For production, you must specify the base URI for the production RaaS API. Make sure not to include /raas/v1 or any trailing slashes.
There are also optional configuration parameters:


A simple wrapper for the Tango Card RaaS API, consisting of two classes: Tangocard::Raas and Tangocard::Response.
Models for each of the Tango Card objects: Tangocard::Account, Tangocard::Brand, Tangocard::Reward, Tangocard::Order and Tangocard::ExchangeRate. These provide a greater level of abstraction and ease of use.
Notes and Credits
This project is developed and maintained by Smartly, Inc.
