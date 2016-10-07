In this topic:

* [What is Bookbinder](#what-is-bookbinder)
* [Why is Bookbinder Used?](#why-is-bookbinder-used)
* [Getting Started With Bookbinder](#getting-started-with-bookbinder)


This topic describes what is Bookbinder, why it's used, and how to get started with it.
For detailed documentation and source code see Bookbinder's [github repository](https://github.com/pivotal-cf/bookbinder).

##What is Bookbinder? ##
Bookbinder is a gem that binds together a unified documentation web application from disparate source material. Source material can be in markdown, HTML, or DITA. All materials must be stored in local directories or in git repositories. Bookbinder runs [middleman](http://www.middlemanapp.com) to produce a Rack app that you can deploy to Cloud Foundry.

##Why is Bookbinder Used? ##
Benefits of using bookbinder are as follows: 
* Allows documentation to be pulled together to form one uniformly templated web application.
* Provides scripts for running on a Continuous Integration system that can detect when a documentation repository has been updated with new content.
* Verifies a composed book is free of any dead links.

##Getting Started with Bookbinder ##

1. Get started with using bookbinder by first cloning the main Cloud Foundry Documentation Repository from [github](https://github.com/cloudfoundry/docs-book-cloudfoundry).

2. Fork and clone or create a repository for documentation being written. Keep in mind the directory that is being cloned or created needs to be a directory that is a sibling to this book repository. If documentation were being conributed to buildpacks, the file structure would look like the following locally:

	<pre>
	|
	+-- docs-book-cloudfoundry
	|
	+-- docs-buildpacks
	|
	</pre>

3. Run bookbinder on local changes:
	<pre>
	$ cd docs-book-cloudfoundry
	$ bundle install
	$ bundle exec bookbinder watch
	</pre>
Bookbinder assembles the document set from local copies.
It skips any topic repositories that are not checked out. For more information on Bookbinder, see the [Bookbinder README](https://github.com/pivotal-cf/bookbinder#bookbinder). 

4. Point the browser at <code>localhost:4567</code> to preview changes. On save, the browser will reload with any additional changes made. The url <code>localhost:4567/__middleman</code> can be used to view resources and links that are available for viewing.



