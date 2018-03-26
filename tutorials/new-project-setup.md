# How to set up a new project

So now that you have learned the [basics of git](https://try.github.io/levels/1/challenges/2),
have [set up git properly](https://github.com/fouralarmfire/square-one/blob/master/machine-setup.md#git) on your computer
and know [how to use your terminal](https://learnpythonthehardway.org/python3/appendixa.html),
you can use both to manage your projects and exercises as you learn.

This tutorial will cover the steps you should take every time you start a new
project.

## tldr summary of commands
For if you have already read the whole way through this tutorial and are just
back here to remind yourself of the process.
(If this is your first time here, please jump to [Part 1](https://github.com/fouralarmfire/square-one/blob/master/tutorials/new-project-setup.md#part-1-create-your-project-locally).)

- do not type the bits after `#`; they are just notes
- words inside `<>` are placeholders, replace them with your details

```sh
cd ~/code && mkdir <new-project-name> && cd <new-project-name> # create project directory
git init # initialise git tracking for your local version

# log into your github account in a brower and create a new repository by clicking the plus at the top right

git remote add origin <url of your repo online>

echo "<project details>" >> README.md # optional, you can also do this later or write a longer one in a text editor

git status # see that there is a new untracked file
git add README.md # track that file
git status # see that the file is now tracked
git commit -m "first commit - adds readme" # commit to the state of your project
git log # see the (short) commit history of your project
git push -u origin master # push your local version to the cloud

# refresh your browser and see your online remote version has been updated

# write some code

git status # see the new code you have written is untracked
git add <file(s) you want to track>
git status # see the new file(s) are now tracked
git commit -m "<brief message about what has changed in/been added to your project>" # commit to the new state/version
git log # see your growing history
git push # push your new stuff to the cloud
```


## Part 1: Create your project locally
Your project will exist in two locations: the `local` version and the `remote`
version. The local version is the one which exists on your computer. The remote
is the version stored in the cloud on Github.

So let's begin by opening `iTerm` or `terminal`, and creating the local version.

**Steps**:

1. Chose a place on your computer to create your project. Most coders tend to
	keep all their projects inside a directory called either `code` or
	`workspace`. This directory is usually in their user `home` directory.
	If you already have a directory to store all your projects you can skip ahead
	to step 2.

	You can get to your `home` directory by running `cd ~` or simply `cd`. When
	you are there you can run `ls` and you should be able to see the folders
	you are used to seeing in `Finder` (`Documents`, `Downloads`, `Applications`,
	etc.).

	When you have decided on the name to call you main coding directory, create it
	and change into it.

	```sh
	mkdir code
	cd code
	```
1. Now we have a dedicated folder to store all our projects in, we can go ahead
	and create a directory for our first project. We are going to be creating a
	simple `hello-world` terminal program, so let's call our project that:

	```sh
	mkdir hello-world
	cd hello-world
	```

	Run `pwd` to check that you are in the right place. You should see `/Users/<your-name>/code/hello-world`.

1. Next we want to use `git` to track this project as we build it. It's best to
	do this from the start. Run `git init` and you should see `Initialized empty
	Git repository in /Users/<your-name>/code/hello-world/.git/`.

	**note**: It is important that you always check that you are in the right
	place before you start working with git. Use `pwd` to see you are in the
	correct project directory, and then `ls` to ensure that only the files that
	are related to that project are visible. (There should be none if you have
	only just created that directory.) Any files in that directory could
	end up being stored publicly in the cloud, so take care not to include
	anything which is sensitive or private.

## Part 2: Create the remote version
Now you need to setup the corresponding project in the cloud.

**Steps**:

1. Open your browser and go to [Github](https://github.com).
1. Once you have logged in, click the plus sign at the top right of the page,
	and select `New repository` at the top of the drop down.
1. In the `Repository name` section write `hello-world`.
1. Click `Create repository`.

And that's it. Now we need to link the local and the remote.

## Part 3: Connecting the two

After we clicked `Create repository`, Github gave us a helpful list of commands
to run, so that is what we are going to do. As this is not an existing repo,
but a brand new one, we are going to use the commands suggested in the first
section. **Note**: We are going to be running these commands in a slightly
different order, so don't go copying and pasting the whole lot.

**Steps**:

1. Creating the link between the local and the remote is very easy: you simply
	need to give the local version the URL of the remote version.
	(You can copy and paste the URL from the 5th line of the commands which Github
	gives you.)

	```sh
	git remote add origin git@github.com:YOUR_USERNAME/hello-world.git
	```

	What is this command doing? The `remote` and `add` are self-evident, given we
	are trying to add a link to a remote repository. `origin` here is the shorter
	name that your computer will use to identify that the remote repository the URL
	points to is the main (original) version of this project.

	If you run `git remote -v`, you'll see that your project URL is saved with the
	`origin` tag.

## Part 4: First commit
**Steps**:

1. The first thing we are going to do is create a README.md. READMEs are a very
	old convention in computing and the clue to what they do is in their name.
	Every project comes with a file which in big, eye-catching capitals, invites
	users of the program to read the file first, before trying to use it.
	This was very important back in the 60s and 70s when computers were instructed
	by punch cards and the whole process of getting a computer and program to run
	was very involved and laborious: you needed a good set of instructions.
	We still use READMEs for the same thing today. They serve as descriptors and
	introductions for projects and what they do, and offer instructions for how
	to run and use the program. On Github, the README.md always serves as the
	landing page in a repository.

	As our project is not really going to be doing much, we are just going to create
	a short README explaining what it does. We can create a new file and write to
	it with just one command in the terminal. Github is telling us how to do that
	with `echo` (`echo "# hello-world" >> README.md`). This command uses `echo`, which 
	we saw when learning about the command line is a command which can print words
	in the terminal. In this command, however, we are telling it that instead of
	just repeating the word back to us in the terminal, we would like to write that
	line into a file. If the file does not exist it will create it, and if it does
	exist, it will append the line to the end of the file. (to overwite an existing
	file completely we would switch `>>` for `>`.)

	So we are going to use `echo` to create a file with just one line in it:

	```sh
	echo "# learning about git" >> README.md
	```

1. Now that we have created the first file in our project, we want git to track
	it.

	If you run `git status`, you should see that git is aware of a new file in the
	directory, but that it is still `untracked`. Git has given us a hint as to how
	we can start tracking files: `use "git add" to track`.

	So lets add our README: `git add README.md`

	Now when we run `git status` again, we can see that (this time in green), git
	knows that we want it to track a new file.

1. But we are not done yet. Git knows that we want to track this file, but we haven't
	yet confirmed that we want to `commit` to this version and save the current state. 
	Are we happy that our project is in a good state that we want to share with
	the world?

	Right now we just have a README so we don't have much to consider, although if
	you want to change your README, you can open it up, write more, and run `git add`
	again. (You have to run `git add` whenever you change a file or git wont save
	those alterations for you.)

	Our README is in a good enough state, so now we are going to commit to that.
	When we make a `commit` we have to add a clear, concise message about what
	is new about this version or state. This is very useful when going back over the
	history of a project. Coders have to read old commit messages every day to quickly
	figure out what a section of code does and why it was written.

	To commit your README run:
	```sh
	git commit -m "first commit, adds readme"
	```

	After that run `git log`. You should see that today, you made your first commit
	in which you added a README.

## Part 5: Pushing to the cloud
**Steps**:

1. Now we need to make the remote version match the local version.
	To do that, we have to `push` our commits to our remote:

	```sh
	git push -u origin master
	```

	We know what `push` and `origin` mean, but what are `-u` and `master`?
	Let's start with `master`. If you run `git branch`, you should see `* master`.
	The git workflow is based entirely around branches. Every project has one main
	branch, `master`: this is the version of your project which must always be kept
	in a fully working state. You should never commit broken or in-progress code
	to master.

	If you have any new ideas, or experiments you want to test out, they should be
	built on a parallel branch. This branch is based upon `master` but will not
	affect it, meaning that people who come to your project will have access to a
	working version you can be proud of. Branches are also useful for when you don't
	quite have time to finish something that day, but you still want to save your
	work for later.

	When your experiments work out, or you finish that new idea, you can pull those
	commits onto master, and carry on normally.

	We will go over how to work with more branches later; for now let's just stick
	with `master`.

	`-u` stands for `upstream`. The `upstream` version is the main source of your
	project. You may think the main source is your computer but no. As your project
	is publicly viewable, and as you may spill coffee on your computer at any moment,
	the main remote repo is the `upstream`. Your computer holds a `downstream` version.
	The work you do is done `downstream` and is then pushed to the official `upstream`.
	A project can have many `downstream`s, and this is how many people can collaborate
	on the same project: by regarding the `upstream` as the source.

1. Once you have pushed, you can go back to Github and refresh that new project page.
	You should see your README instead of the git commands.

	Congratulations! You have set up your project and are now ready to get to work.

## Part 6: Writing and publishing our first program
We are going to be writing some actual code now, and learning some more about the
command line and how your computer runs programs.

**Steps**:

1. Complete the first [Hello World](https://github.com/fouralarmfire/square-one/blob/master/tutorials/hello-world-1.md#hello-world-1) exercise.
1. When your `hello` program is working (i.e. you can run `./hello` in the terminal
	and see `Hello World!` printed back to you), run `git status`. You should see
	that there is a new untracked file in your project.
1. Run `git add hello` to track your program.
1. Run `git status` again to verify that it is being tracked.
1. Run `git commit -m "new 'hello' program - says Hello World!"` to commit your new
	project state.
1. Run `git log` to see your growing project history.
1. Finally we can run `git push` to send our code to the remote version.

	**Note**: this time we did not need to run the push command with `-u origin master`.
	That is because git stored the information about which upstream branch we want
	to use as the main one. From now on, all we need to say is `git push`.

1. You can now navigate to the online repo in your browser, and see your `hello` program.


## Part 7: Taking notes

Since we are learning new things, it would be handy to use the README of our repo
to document what we have learned after each section. The `.md` extension stands
for markdown and you can learn how to render documentation using markdown [here](https://guides.github.com/features/mastering-markdown/).

**Steps**:

1. Open your README.md in a text editor. 
1. Summarise what you have learned so far.
1. Commit and push your changes.

	```
	git add README.md
	git commit -m "update readme: parts 1 to 6 notes"
	git push
	```

From now on, for every project or tutorial you do, take notes on what you learn
like this so that you keep them together with the code you write.

### This tutorial is a work in progress. Refresh regularly for updates.