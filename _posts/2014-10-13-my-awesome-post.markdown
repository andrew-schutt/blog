---
layout: post
title: "My Awesome Post"
date: 2014-10-13T20:30:44-05:00
---

<code>$ git-init</code>

Github is a <a href="https://en.wikipedia.org/wiki/Distributed_revision_control" target="_blank">distributed revision control system</a> that I use to track my work. Really though <a title="Github" href="https://github.com/" target="_blank">Github</a> is so much <a title="techcrunch article on github" href="http://techcrunch.com/2012/07/14/what-exactly-is-github-anyway/" target="_blank">more</a>. I am taking the time today to briefly cover how to initialize a new repo for Github. This will walk through the first couple of commands that are used to kick off a project in the beginning.

<a title="The official Github help page on this topic of creating a new repo" href="https://help.github.com/articles/create-a-repo" target="_blank">Here is the official Github help page related to this topic.</a> I don't find it to particularly useful though since most of the work that I do with Github is by issuing Terminal commands.

If you don't have Git setup on your local machine you have some one time hoops to jump through before getting started. <a title="steps for setup of git" href="https://help.github.com/articles/set-up-git" target="_blank">Go follow these steps.</a> They involve downloading and installing Git, doing a bit of account creation and setup, and lastly getting your connection secured for communicating with Github.

Now, back to creating a new Github repo. First within terminal navigate to the top folder level of the project you wish to create a repo for. From terminal issue this command.

<code>$ git <a href="http://git-scm.com/docs/git-init" target="_blank">init</a></code>

You should see a message similar to this.

<code>Initialized empty Git repository in home/developer/public_html/.git</code>

Within that same level of the folders issues the command.

<code>$ git <a href="http://git-scm.com/docs/git-add" target="_blank">add</a> *</code>

This commands tags all of the files that are to be added when we issue a commit command which is what we shall do next.

<code>$ git <a href="http://git-scm.com/docs/git-commit" target="_blank">commit</a> -m 'first init commit'</code>

You will see a list of the files being committed within your terminal window. When this is all finished up go ahead check in on the status.

<code>$ git <a href="http://git-scm.com/docs/git-status" target="_blank">status</a></code>

And this is the message that you should see.

<code>On branch master
Untracked files:
(use "git add ..." to include in what will be committed)</code>

.project
nothing added to commit but untracked files present (use "git add" to track)

Now we need to actually get this tied to the Github site so we can do a push up to repo on Github.com. <a href="https://help.github.com/articles/creating-a-new-repository" target="_blank">Here are the steps needed to accomplish that.</a>

Once that new repository is created we need to grab the url for that repo and issued the following commands.

<code>$ git <a href="http://git-scm.com/docs/git-remote" target="_blank">remote</a> add origin ADDRESS_OF_REMOTE_REPO</code>

<code>$ git <a href="http://git-scm.com/docs/git-push" target="_blank">push</a> -u origin-master</code>

There we go. We now have a new working git repo. Good times. Here is a listing of just the commands that we used.

<code>$ git init</code>
<code>$ git add *</code>
<code>$ git commit -m 'first init commit'</code>
<code>$ git remote add ADDRESS_OF_REMOTE_REPO</code>
<code>$ git push -u origin-master</code>