---
layout: post
title: "Starting a Rails App"
date: 2015-01-18T14:06:33-06:00
---
Alright, here it is.  The long anticipated how to start a rails app blog post. Finally.

<h4>Install Ruby</h4>
First things first though.  Do you have <a href="https://www.ruby-lang.org/en/">ruby</a> installed?  If you are on a Mac then the answer is yes.  Ruby comes shipped with ruby <code>1.8.7</code>.

It is highly recommended that you upgrade this version for a bunch of reasons.  Just google and take my word for it though.  <code>1.9.0</code> brought about some major upgrades to speed and functionality for the language while <code>2.0.0</code> brought some more of all that good stuff.  If your not sure what version you have go ahead jump into the Terminal application and just type <code>ruby -v</code>.  This will spit back a result with the version for you. 

To go about upgrading your version of ruby is really outside of the scope of "starting a rails app", but I will say I personally use <a href="https://rvm.io/rvm/install">RVM</a> and rather enjoy it.  

<h4>Install Rails</h4>
So, you have ruby that's one half of the whole 'Ruby on Rails' thing.  Time for the rails part.  What does that entail?  Let's go grab <a href="https://rubygems.org/pages/download">ruby gems</a> this is handy (irreplaceable) tool for package managment within ruby. You will likely use this quite a bit in any future ruby development that you do.  I predict we will be using in the very near future... like right now to install rails actually.

Still have the terminal open from before to check what version of ruby you have?  Great.  Next we will be navigating to a place on your file system that you like to keep projects and make a directory to house our rails project.  Then go into the newly created folder.
<pre>
<code>cd ~/Documents</code>
<code>mkdir rails_application</code>
<code>cd rails_application</code>
</pre>
Now we do a little ruby gems magic.  

<code>gem install rails</code>

This can take a little bit of time as it reterives all of the necessary pieces that make up <a href="http://www.github.com/rails/rails/">rails</a>.  When that is all finished up though we have now installed the rails half of 'Ruby on Rails' and that's the whole shabang.  

<h4>Pulling it all together</h4>
Let's get started then.  In the command prompt type the following.

<code>rails new foo_bar</code>

This is a built in Ruby on Rails command that will generate the basic pieces that we need in order to create our rails application.  The 'foo_bar' part is the name of our newly created application.  Feel free to do whatever you want.  

If you do a quick <code>ls</code> command you will see that we have another newly created folder called <code>foo_bar</code> (unless of course you named yours something different!).  <code>cd</code> into this newly created folder and issue another <code>ls</code> command.

This is loosely what you should see.

<code>Gemfile README.rdoc app\ config\ db\ log\ test\ vendor\
	  Gemfile.lock Rakefile bin\ config.ru lib\ public\ tmp\</code>
	  
I highly recommend exploring a bit from here.  The <code>app</code> directory is where the pieces that make up your application will live.  These pieces include the code that will make up your models, views, and controllers.  The other folders are for various key components outside of what your application is.  

Now the most powerful piece of rails is that we have now 'created' a rails application.  From the top level directory of our application <code>~/Documents/rails_application/foo_bar/</code> we can issue the command <code>rails server</code> and our rails app is all started up and running locally.  In the output after issuing that command look for the <code>port=xxxx</code> (mine is port 3000 yours likely will too).  Open up your favorite web browser and go to localhost:3000.

Boom! We have ourselves the most basic rails app imagainable that does nothing, but hey, it's a rails application none the less.  Later we will explore the individual pieces that make up the rails app and discuss each.