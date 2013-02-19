rails-no-db
===========

Proof of concept for running rails without a data store.

To generate a minimalist rails app with no datastore you can invoke the following command line:

$ rails new <app_name> -OSJ

The options used are as follows:

  -O, [--skip-active-record]     # Skip Active Record files

  -S, [--skip-sprockets]         # Skip Sprockets files

  -J, [--skip-javascript]        # Skip JavaScript files

The option we are concerned with the most for this proof of concept is -O which
skips the creation of defaults for using the ActiveRecord libraries.

You can notice that there is no database.yml file in the config/ directory.
Also, the require statement for ActiveRecord is commented out in config/application.rb.

This proof of concept has a single route with the root pointing to the 'index' method in the 'home' controller.
This causes the template in app/views/home/index.html.erb to be displayed.

To run this proof of concept clone the repository, run 'bundle install', start the server and open a browser to localhost:3000.
e.g.:

git clone git://github.com/shawnpage/rails-no-db.git

cd rails-no-db

bundle install

./script/server rails s

http://localhost:3000

You should see the 'Hello, Rails' message.
