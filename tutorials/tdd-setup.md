# Windows

#### Ruby
1. Check whether Ruby is installed with: `ruby --version`
	1. If you don't see something like `ruby 2.5.0p0 (2017-12-25 revision 61468)`,
			you will need to [install Ruby](https://rubyinstaller.org/).
	1. Once the installers have run, select `Start Command Prompt with Ruby` from your start menu.
	1. Verify that Ruby is now installed with: `ruby --version`

#### Git
1. Check whether `git` is installed with: `git --version`
	1. If you don't see something like `git version 2.9.2`,
			you will need to [install Git](https://gitforwindows.org/). Say yes to the
			defaults during the wizard installation. At the end select `launch git` which
			which should open a bash emulator app.
	1. Verify that git is now installed with: `git --version`

1. Log into [Github](https://github.com/) or sign up if you have not already done so.
1. New to git?
	1. [Sign up](https://github.com/).
	1. In your bash emulator, run the following two commands to save your login information to your computer.
		Every time you "push" (save) code to git, these credentials will be used to identify you.
		(The things in caps are placeholders, please use your actual information.)

		```
		git config --global user.email "YOUR EMAIL ADDRESS"
		git config --global user.name "YOUR GITHUB USERNAME or ACTUAL NAME"
		```

	1. Run `ssh-keygen -t rsa -b 4096 -C "YOUR EMAIL ADDRESS"`. (Hit return to any prompts until complete.)
	1. Start the SSH agent with `eval "$(ssh-agent -s)"`. ([SSH](https://www.digitalocean.com/community/tutorials/ssh-essentials-working-with-ssh-servers-clients-and-keys) is a form of security)
	1. Add your new key to the agent: `ssh-add ~/.ssh/id_rsa`.
	1. Copy your the contents of `~/.ssh/id_rsa.pub` to the clipboard.
	1. Login to Github in a browser. Go to `Settings > SSH and GPG keys > New SSH key / Add SSH key`.
	1. Fill in the form fields with a name and your copied public key and click save.
	1. You may want to complete a [quick tutorial](https://try.github.io/) first.

#### Atom
1. If you do not already have a text editor, go to [atom.io](https://atom.io/)
	and follow installation instructions.

#### Command Prompt
1. Your command prompt can be found in your start menu.


# Mac

#### Ruby
1. Check whether Ruby is installed with: `ruby --version`
	1. If you don't see something like `ruby 2.5.0p0 (2017-12-25 revision 61468)`,
			you will need to [install Ruby](https://www.ruby-lang.org/en/documentation/installation/#homebrew).
	1. Verify that Ruby is now installed with: `ruby --version`

#### Git
1. Check whether `git` is installed with: `git --version`
	1. If you don't see something like `git version 2.9.2`,
			you will need to [install Git](https://gitforwindows.org/). Say yes to the
			defaults during the wizard installation. At the end select `launch git` which
			which should open a bash emulator app.
	1. Verify that git is now installed with: `git --version`

1. Log into [Github](https://github.com/).
1. New to git?
	1. [Sign up](https://github.com/).
	1. In your terminal, run the following two commands to save your login information to your computer.
		Every time you "push" (save) code to git, these credentials will be used to identify you.
		(The things in caps are placeholders, please use your actual information.)

		```
		git config --global user.email "YOUR EMAIL ADDRESS"
		git config --global user.name "YOUR GITHUB USERNAME or ACTUAL NAME"
		```

	1. Run `ssh-keygen -t rsa -b 4096 -C "YOUR EMAIL ADDRESS"`. (Hit return to any prompts until complete.)
	1. Start the SSH agent with `eval "$(ssh-agent -s)"`. ([SSH](https://www.digitalocean.com/community/tutorials/ssh-essentials-working-with-ssh-servers-clients-and-keys) is a form of security)
	1. Add your new key to the agent: `ssh-add ~/.ssh/id_rsa`.
	1. Copy your public key to the clipboard:

		```
		# either
		pbcopy < ~/.ssh/id_rsa.pub
		# or
		cat ~/.ssh/id_rsa.pub | pbcopy
		# these commands are the equivalent of looking at the file and pressing <Command-C>
		```

	1. Login to Github in a browser. Go to `Settings > SSH and GPG keys > New SSH key / Add SSH key`.
	1. Fill in the form fields with a name and your copied public key and click save.
	1. You may want to complete a [quick tutorial](https://try.github.io/) first.

#### Atom
1. If you do not already have a text editor, go to [atom.io](https://atom.io/)
	and follow installation instructions.

#### Terminal
1. Your terminal is found in your Applications and can be opened by typing `cmd+space`
	and then typing `terminal`.
1. Alternatively, you can install [iTerm2](https://www.iterm2.com/downloads.html), which comes with additional features.