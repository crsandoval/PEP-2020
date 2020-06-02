Week 1
======

Throughout this internship we will be using specific tools to work on
the research project. This is a tutorial to help you install those tools
on your computer. These include:

1.  GitHub
2.  Git
3.  R à la RStudio

### Programming expectations

We will be using R and R Markdown files for this internship,
communicating research materials through the use of Git and GitHub.
Knowledge of R is not a prerequisite for this internship, **provided you
are comfortable learning on your own as needed**. Basically, you should
feel comfortable:

-   How to look up R syntax on Google and StackOverflow
-   Basic programming concepts like functions, loops, arrays,
    dictionaries, strings, and if statements
-   How to learn new libraries by reading documentation
-   Asking questions on Slack and StackOverflow

1 - Create your GitHub account
------------------------------

To sign up for an account, just go to [GitHub](https://github.com) and
pick a unique username and supply an email address and a password. Once
you’ve done that, your GitHub page will be at
`https://github.com/<your-username-here>`.

2 - Setting up your Git environment
-----------------------------------

### Installing Git

If Git is not installed on your Windows machine, go to
<a href="http://git-scm.com" class="uri">http://git-scm.com</a>. Accept
all defaults in the installation process. On Windows, installing Git
will also install for you a minimal unix environment with a “bash” shell
and terminal window. We won’t be using the “bash” shell much, if at all,
but you should be aware of it.

#### Windows specific notes

There will be an installer `.exe` file you need to download / click.
Again, accept all the defaults. To see if you were successful, open a
terminal window and type:

`git --version`

If you see something like

`git version 2.25.1.windows.1`

Then the installation was a success!

At this point you will have Git installed. You can bring up “git bash”
either from your start menu, or from the right click menu on any folder
background. When you do so, a terminal window will open. This terminal
is where you could issue further Git setup commands, and Git commands in
general.

### Setting global config for Git

Again, from the terminal, issue the command

`git config --global user.name "YOUR NAME"`

This sets up a name for you. Then do

`git config --global user.email "YOUR EMAIL ADDRESS"`

Use the **SAME** email address you used in setting up your GitHub
account.

These commands set up your global configuration.

3 - Setting up RStudio
----------------------

If RStudio is not installed on your Windows machine, go to
<a href="https://rstudio.com/products/rstudio/download/#download" class="uri">https://rstudio.com/products/rstudio/download/#download</a>.
Accept all defaults in the installation process.
