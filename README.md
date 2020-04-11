# Spree PagSeguroLightbox

Add support for Pagseguro checkout as a payment method.
__Tested on Spree 4.1.1__

This gem approach takes in consideration that a incomplete order with an approved PagSeguro transaction is unacceptable. So the user will complete the order process and then will be guided to PagSeguro to pay.

## Installation

1. Add the following to your Gemfile

    gem 'spree_pagseguro_simple'

2. Run `bundle install`

3. To copy and apply migrations run: `rails g spree_pagseguro_simple:install`

## Configuring

1. Add a new Payment Method, using: `Spree::PaymentMethod::PagSeguro` as the `Provider`

2. Click `Create`, and enter your Store's Pagseguro Email and Token in the fields provided.

3. Define ENV['PAGSEGURO_ENV'] with 'sandbox' or 'production'.

4. `Save` and enjoy!

4. Is important to go to general settings in spree and configure the store url for redirects and notifications

## To-Do

  - Need to add test coverage to gem
  - Configure enviroment to use payment method preference
  - Work in notification controller action
  - Improve view in order#show

Testing
-------

To make real tests register in PagSeguro sandbox and configure the payment method as test.

Be sure to add the rspec-rails gem to your Gemfile and then create a dummy test app for the specs to run against.

    $ bundle exec rake test app
    $ bundle exec rspec spec

Disclaimer
----------

This gem is inspired by [Locomotiva gem](https://github.com/locomotivapro/spree_pagseguro_simple) but updated to spree 4 and using checkout lightbox.
