---
layout: post
title: "How I Created This Blog"
date: 2014-11-08T10:56:45-06:00
---
When I first started blogging I was using a Wordpress site that I hosted on my own, but came across an enlightening <a title="setup a blog in 5 mins from Julia Evans" href="http://jvns.ca/blog/2014/10/08/how-to-set-up-a-blog-in-5-minutes/">blog post</a> from Julia Evans regarding putting your blog up on github and versioning it.  Lately I had been wondering about how I could accomplish a very similar task having recently versioned <a href="http://www.andrewschutt.net">andrewschutt.net</a> using github.  And some day that site is going to get it hosted on github as well.  The benefit of having a site hosted on github is being able to simply issue a git push in order to publish a post.  Oh, by the way you get to this all for the high, high cost of free.

<h4>Setup</h4>
First you will need to do a little setup for your system to getting going with a blogging framework called <a href="http://octopress.org">Octopress</a>.  As mentioned we will be using github for hosting of the blog, so, it will be necessary to have <a href="http://git-scm.com/">Git installed</a>.  Next we will need Ruby 1.9.3 or greater.  Personally I use <a href="http://rvm.io/">RVM</a> to handle my multiple versions of Ruby.

<h4>Setup Octopress</h4>
To setup Octopress you will be using some git commands cloning down the code from github.  From you terminal issue the following commands in the folder that you wish to keep a copy of your blog locally.
<code>gem install octopress --pre</code>

In addition to setting up Octopress you will need to get a new repo to host your blog brimming with fantastic ideas.  

Hop over to Github and create a new repo being sure to call this repo <code>your-username.github.io</code>.  The information pertaining to this on github can be found <a href="https://help.github.com/articles/user-organization-and-project-pages/">here</a> and <a href="https://help.github.com/articles/creating-project-pages-manually/">here</a>.

You now have Octopress setup and now it's time to get a local instance of Octopress up and running locally.

<h4>Create blog</h4>
<code>octopress new blog-name</code>

<code>cd blog-name</code>

<code>octopress serve</code>

Open up a browser and goto http://localhost:4000.  From here you are able to view your newly created blog.

<h4>Deploying blog to Github</h4>
We will be putting this site on into the <code>gh-pages</code> branch of this repository in order to have it publicly available.  Within the local directory <code>blog-name</code> perform the following.

<code>git init</code>

<code>git add .</code>

<code>git commit -m "sterotypical msg for 1st post.  lols"</code>

<code>git remote add origin git@github.com:your-username/blog-name</code>

<code>git checkout -b gh-pages</code>

<code>git push -u origin gh-pages</code>

<h4>Edit the _config.yml</h4>
We have pushed to github, but will still need to make some minor tweaks to the _config.yml file to get thing working right.

Within the _config.yml file edit the line

<code>baseurl: "" # the subpath of your site, e.g. /blog/</code> into <code>baseurl: /blog-name # the subpath of your site, e.g. /blog/</code>

You also can edit some other fields in here to get you twitter and github username linked at the bottom of you blog.

<h4>Go blog</h4>

Now comes the hard part.  Typing up your thoughts and sharing ideas.  Doing this consistently is difficult and easy to lose track of.  Hopefully with this low barrier to posting will help encourage your blogging!

<code>rake new_post["title"]</code>
