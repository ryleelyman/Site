---
layout: post
---
As a mathematician,
I collaborate with other mathematicians on papers.
I've used Overleaf, emailing the paper back and forth,
and taking turns in Dropbox as my mode of collaboration.
I *haven't* collaborated using Git, but I sure would like to.
The purpose of this post is for mathematicians
like for example my younger self,
who are familiar with the command line
and curious about Git as a tool,
and for whatever reason don't have the patience for something like "Git for Poets."
I explain Git just enough to get you started on a simple project,
and hopefully enough so that you can start
Googling things you're unfamiliar with.
I'm not an expert, and I expect my inexpertise to show.

Let's start. There are two ways I typically start.
The first way is 
that I have files on my computer that I would like to use Git on.
So I would open a command line,
`cd` over to where those files are (say `~/Documents/waver`) and invoke
`git init`.
This starts a new Git repository in the folder you're in.

The other way is some Git repository already exists
(probably on GitHub)
and I would like to work on those files.
In that case I would find the URL of that repository,
`cd` to the directory where I would like to put my copy of the repository,
and invoke
`git clone <url>`.
This automatically creates a new folder with the contents of the repository,
so if I was cloning `ryleelyman/waver` on GitHub, for instance,
and I wanted it to end up in `~/Documents/waver`,
I would run `git clone https://github.com/ryleelyman/waver.git` 
in my `~/Documents` folder.

Now Git is paying attention to the files in `~/Documents/waver`,
but by default it isn't doing anything to them at all.
You can see what it thinks by invoking `git status`.
If you have files that have changed,
Git will display them (in red, in my terminal).
For example, when I run `git status` in the
directory for my website, it tells me
```
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   _site/blog.html
        modified:   _site/feed.xml
        modified:   _site/sitemap.xml
```

Git tracks changes based on "commits,"
but in order for something to be committed
Git needs to know that you want to commit it.
That's the business of the `git add <file>` comment above.
If we were to do `git add _site/blog.html`,
we would be telling Git to prepare to commit
the changes we made to the `_site/blog.html` file.
To actually commit the changes from there we would do
`git commit`.
But! Don't actually do `git commit`.
I prefer `git commit -m "<message>"`.
Git commits require a little blurb from you about the changes,
and I find it much more convenient to just write that message
on the command line.

Now Git knows about our changes locally.
If we're working with a remote repository, say on GitHub,
we still need to update that repository.
To do that we invoke `git push`.
If you started the repository with `git init`,
you may need to setup GitHub (or whatever it is)
to track the repository you created. 
GitHub has nice instructions for this.
To update our local repository with changes from the remote repository,
we would do `git pull`.

Those are all the commands I use daily.
I didn't talk about Gits "branching" model,
which is worth learning a bit about.
I don't know that I have anything cogent to say about it,
so maybe I'll stop here.
