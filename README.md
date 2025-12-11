# My dotfiles

This directory contains the dotfiles for my system. 

## Requirements

Ensure you have the following installed on your system:

### Git & Stow

On Arch and Debian:

```bash
sudo pacman -S git
sudo pacman -S stow
```

On Ubuntu:

```bash
sudo apt install git
sudo apt install stow
```

On RHEL-based systems (RedHat Enterprise Linux, Fedora, CentOS, Oracle Linux, Rocky, etc.)

```bash
sudo dnf install git
sudo dnf install stow
```


## Installation

First, check out the dotfiles repo in your $HOME directory using git:

```bash
git clone git@github.com:rmonin/dotfles.git ~/.dotfiles 
cd dotfiles
```

Then use GNU stow to create symlinks (-v makes stow tell us what it's doing while it's doing it):

```bash
$ stow -v .
```

You can also watch the video from [Dreams of Autonomy](https://www.youtube.com/@dreamsofautonomy) about Stow: [Stow has forever changed the way I manage my dotfiles](https://www.youtube.com/watch?v=y6XCebnB9gs) and the [git repo](https://github.com/dreamsofautonomy/dotfiles) where this one is inspired by, together with the Makefile from [rmonin](https://github.com/rmonin/dotfles/blob/main/Makefile) on GitHub.
