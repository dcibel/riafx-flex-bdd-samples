B.D.D with Flex, getting started
================================

I'll assume that you have Flash Builder, Ruby and Gem installed.

Get required gems
-----------------
If you use [RVM](https://rvm.beginrescueend.com/), don't forget to [create a gemset](http://beginrescueend.com/gemsets/basics/).

* melomel : Ruby <-> Flash communication
* cucumber : B.D.D. tool
* rspec : used by melomel cucumber steps to define expecations
* selenium-webdriver : used to run you Flex application from the browser

One command line to get them all:

    gem install melomel cucumber rspec selenium-webdriver

You're ready to run the HelloWorld sample !

Compile the project in Flex.

cd into the HelloWorld project and run
    cucumber

If you want to setup a new project
----------------------------------

1. Create a new Flex Project
2. Download melomel-x.y.z.zip from [melomel's github download page](https://github.com/benbjohnson/melomel/archives/master)
3. Add the melomel-x.y.z.swc file to your project (using the libs folder for example). The melomel-stub should be used for release (it's an empty implementation).
4. In your application's main mxml file, add <m:Melomel/> to fx:Declarations with namespace xmlns:m="library://melomel/2010"
5. Create features/step_definitions and feature/support directories
6. Create features/support/env.rb with following content (make sure to define the path to your appliation) :
        require 'rubygems'
        require 'rspec'
        require 'cucumber'
        require 'selenium-webdriver'
        require 'melomel'
        require 'melomel/cucumber'
        
        Before do |scenario|
          @driver = Selenium::WebDriver.for :firefox
          @driver.navigate.to "file:///absolute/path/to/your/app.swf.or.html"
          Melomel.connect()
        end
        
        After do |scenario|
          @driver.quit() unless @driver.nil?
        end


Useful links
------------
*  [Melomel official website](http://melomel.info/)
*  [Cucumber steps provided by Melomel](http://melomel.info/Cucumber)
*  [Melomel examples](https://github.com/benbjohnson/melomel-examples)


About versions...
-----------------
Theses sample projects were tested with the following configuration:

* Flex 4.1
* Ruby 1.9.2
* cucumber 0.10.2
* melomel 0.6.2
* rspec 2.5.0
* selenium-webdriver 0.2.0
