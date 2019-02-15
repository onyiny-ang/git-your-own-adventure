# Before you begin:

### Git Set Up

This workshop requires that you have an existing github account that you can
push to. On some versions of github (earlier than 1.7.10), pushing through https is not straight forward, but in any case, it might be a good idea to set up your [ssh-key](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/). Follow the steps to `generate a new SSH Key` and `add you ssh key to the ssh-agent`. Then [link it to your github account](https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/)

You can check your git version with:

```
git version
```

You should also set up your git config with your username and email for the
commits you make to github so your commits will be signed by you!:

```
git config --global user.name "<Your-github-user-name>"
git config --global user.email "<your-email@example.com>"
```

You can check your git config details with:

```
git config -l
```

### Command line tools

This tutorial also assumes that you know some basic linux commands and is primarily helpful if you want to use the command line to interact with git repositories.
The tools used in this tutorial are: `cd`, `mkdir`,`touch`, `echo`, `ls` which are all covered
[here](https://maker.pro/linux/tutorial/basic-linux-commands-for-beginners) if
you need a refresher.


[Now I'm ready to start!](START-HERE.md)
