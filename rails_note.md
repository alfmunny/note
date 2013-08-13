### scaffold

to create a scaffold model

	$ rails generate scaffold Myfoo

to delete a  scaffold model

	$ rails destroy scaffold Myfoo

*by the way a trick for VIM to insert the current date*

	:r !date
*actually you can always run the shell command in VIM and insert the outputs like this*
	
	:r !command

in Rails 4 attr_accessible has been moved away. To use it,add this line to your application's Gemfile

	gem 'protected_attributes'
then

	$ bundile
	
###Gemfile

add this lines

	ruby 1.9.3

	group :development, :test do
		gem 'pg'
	end

this one has been already mentioned above

	gem 'protected_attributes'

###completion for Ruby

install the plugin ruby.vim, rails.vim.

	C-X,X-O

`2013年 6月 9日 星期日 18时12分25秒 CEST`


###rubytest

<Leader>t: run test case under cursor
<Leader>T: run all tests in file
<Leader>l: run the last test, from any buffer

###fuzzyfinder

        <CR>  (|g:fuf_keyOpen|)        - opens in a previous window.

        <C-j> (|g:fuf_keyOpenSplit|)   - opens in a split window.

        <C-k> (|g:fuf_keyOpenVsplit|)  - opens in a vertical-split window.

        <C-l> (|g:fuf_keyOpenTabpage|) - opens in a new tab page.
	
###Test with Guard

	1. $ rails s
	
	2. $ guard

	3. $ run the test in *.html.erb with Rubytest

`2013-06-13`

###push to heroku

befor push to heroku, must first compile the CSS on local

	RAILS_ENV=production bundle exec rake assets:precompile

set the assets in *production.rb* to true

	config.serve_static_assets = true 

### change datebase

configure the config/datebase.yml

	$ vi config/datebase.yml

	development:
		adapter: postgresql
		database: my_database_development 
		pool: 5
		timeout: 5000
	test:
		adapter: postgresql 
		database: my_datbase_test 
		pool: 5 
		timeout: 5000

	production:
		adapter: postgresql 
		database: my_datbase_production 
		pool: 5 
		timeout: 5000 

then run rake

	$ rake db:create

	$ rake db:migrate

`2013-06-24`
