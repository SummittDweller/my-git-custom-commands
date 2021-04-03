The contents of this directory were inspired by https://levelup.gitconnected.com/automate-repetitive-tasks-with-custom-git-commands-76a4b71d262f.
In case that post is ever deleted...

## Automate repetitive tasks with custom Git commands

Srebalaji Thirumalai
May 14, 2020 · 4 min read

Git helps us to write our own custom commands, and these commands can be written in any language you prefer like Ruby or JavaScript.

In this tutorial, I will explain how to write your own custom commands, and I will give some examples of it. We will be using bash for this tutorial.

Writing custom git commands are simple as these three steps:

  - Create a file with a name in the given format git-mycommand. And this file should be given executable access.
  - The created file should be included in $PATH. This can be done in bashrc or in zshrc
  - Then you can run the command git mycommand in any of the git repo you have.

### Writing our first custom command

Let’s write a custom Git command to add, commit, and then push the changes to remote with one command.

1. Creating a file for our command

It’s good to have a directory to contain all our custom commands so that it will be organized. Let’s create a directory.

  `mkdir my-git-custom-commands`

Create a file named git-lazypush in the above created directory and add the following code. Refer to the code in the gist here.

Last but not least, make that file as executable

  `chmod +x git-lazypush`

2. Add custom commands to $PATH

This is quite important. This will help Git to recognize the custom commands.

We are adding the directory to $PATH. Add the following line to bashrc or to zshrc

  `export PATH=$PATH:/your-directory/my-git-custom-commands`

You can now source the file or start a new instance of the terminal

  `source ~/.zshrc`

3. Running our custom command

With everything in place, it’s time to run our custom command. Go to any of your local git repo and run the following command

  `git lazypush "Your commit message"`

As you can see, I have created a new file and have executed the custom command.

And it is evident that files are added, committed, and pushed to the remote server.

Git commands are very useful and can be used to automate the usual tasks in your workflow. So try to find tasks you find repetitive and automate it.


