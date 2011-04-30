
B.D.D with Flex, getting started
================================

I'll assume that you have Flash Builder, Ruby and Gem installed.

Get required gems
-----------------
If you use [RVM](https://rvm.beginrescueend.com/), don't forget to [create a gemset](http://beginrescueend.com/gemsets/basics/).

* melomel : Ruby <-> Flash communication
* cucumber : B.D.D. tool
* rspec : used by melomel cucumber steps to define expecations

One command line to get them all:

    gem install melomel cucumber rspec

You're ready to run the HelloWorld sample !
-------------------------------------------

If you want to setup a new project
----------------------------------

1. Create a new Flex Project
2. Download melomel-x.y.z.zip from [melomel's github download page](https://github.com/benbjohnson/melomel/archives/master)

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
